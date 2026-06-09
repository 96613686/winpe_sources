# SymSrvGetFileIndexInfoW

- ea: `0x180019280`
- end: `0x1800193f5`
- name: `SymSrvGetFileIndexInfoW`
- size: `373`
- prototype: `BOOL __stdcall(PCWSTR File, PSYMSRV_INDEX_INFOW Info, DWORD Flags)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1801ae500`

## callees

- `0x180009790`
- `0x180019280`
- `0x1800193fc`
- `0x1800273f0`
- `0x180027430`
- `0x18019110c`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019314`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019314`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019337`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001936d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019337`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001936d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192bb`

## pseudocode

```c
BOOL __stdcall SymSrvGetFileIndexInfoW(PCWSTR File, PSYMSRV_INDEX_INFOW Info, DWORD Flags)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  WCHAR *v10; // rcx
  __int64 v11; // rax
  wchar_t Source[264]; // [rsp+50h] [rbp-238h] BYREF

  if ( Info->sizeofstruct != 1608 )
  {
    SetLastError(0x57u);
    return 0;
  }
  memset_0(Info->file, 0, 0x644u);
  Info->sizeofstruct = 1608;
  _wsplitpath_s(File, 0, 0, 0, 0, Info->file, 0x105u, Source, 0x101u);
  if ( Info == (PSYMSRV_INDEX_INFOW)-4LL )
  {
    *(_DWORD *)_o__errno(v7, v6, v8, v9) = 22;
  }
  else
  {
    v10 = Info->file;
    v11 = 261;
    while ( *v10 )
    {
      ++v10;
      if ( !--v11 )
      {
LABEL_8:
        Info->file[0] = 0;
        *(_DWORD *)_o__errno(v10, v6, v8, v9) = 34;
        goto LABEL_15;
      }
    }
    v10 = Source;
    while ( *v10 )
    {
      ++v10;
      if ( !--v11 )
        goto LABEL_8;
    }
    wcscat_s(Info->file, 0x105u, Source);
  }
LABEL_15:
  if ( !extmatch(File, L".pdb") )
    return ReadImageIndexInfo(File, Info);
  if ( !(unsigned int)diaGetPdbIndexInfo(File, &Info->guid, &Info->age) )
    return 0;
  if ( !Info->guid.Data2 )
    Info->sig = Info->guid.Data1;
  return 1;
}

```

## disassembly

```asm
0x180019280  mov     [rsp+arg_10], rbx
0x180019285  mov     [rsp+arg_18], rbp
0x18001928a  push    rsi
0x18001928b  push    rdi
0x18001928c  push    r14
0x18001928e  sub     rsp, 270h
0x180019295  mov     rax, cs:__security_cookie
0x18001929c  xor     rax, rsp
0x18001929f  mov     [rsp+288h+var_28], rax
0x1800192a7  mov     edi, 648h
0x1800192ac  mov     rbx, rdx
0x1800192af  mov     rsi, rcx
0x1800192b2  cmp     [rdx], edi
0x1800192b4  jz      short loc_1800192C8
0x1800192b6  mov     ecx, 57h ; 'W'; dwErrCode
0x1800192bb  call    cs:__imp_SetLastError
0x1800192c1  xor     eax, eax
0x1800192c3  jmp     loc_1800193CD
0x1800192c8  lea     rcx, [rdx+4]; void *
0x1800192cc  mov     r8d, 644h; Size
0x1800192d2  xor     edx, edx; Val
0x1800192d4  call    memset_0
0x1800192d9  mov     [rsp+288h+ExtCount], 101h; ExtCount
0x1800192e2  lea     rax, [rsp+288h+Source]
0x1800192e7  mov     [rsp+288h+Ext], rax; Ext
0x1800192ec  mov     r14d, 105h
0x1800192f2  mov     [rbx], edi
0x1800192f4  xor     ebp, ebp
0x1800192f6  mov     [rsp+288h+FilenameCount], r14; FilenameCount
0x1800192fb  lea     rdi, [rbx+4]
0x1800192ff  mov     [rsp+288h+Filename], rdi; Filename
0x180019304  xor     r9d, r9d; Dir
0x180019307  xor     r8d, r8d; DriveCount
0x18001930a  mov     [rsp+288h+DirCount], rbp; DirCount
0x18001930f  xor     edx, edx; Drive
0x180019311  mov     rcx, rsi; FullPath
0x180019314  call    cs:__imp__wsplitpath_s
0x18001931a  test    rdi, rdi
0x18001931d  jz      short loc_18001936D
0x18001931f  mov     rcx, rdi
0x180019322  mov     eax, r14d
0x180019325  cmp     [rcx], bp
0x180019328  jz      short loc_180019345
0x18001932a  add     rcx, 2
0x18001932e  sub     rax, 1
0x180019332  jnz     short loc_180019325
0x180019334  mov     [rdi], bp
0x180019337  call    cs:__imp__o__errno
0x18001933d  mov     dword ptr [rax], 22h ; '"'
0x180019343  jmp     short loc_180019379
0x180019345  lea     rcx, [rsp+288h+Source]
0x18001934a  cmp     [rcx], bp
0x18001934d  jz      short loc_18001935B
0x18001934f  add     rcx, 2
0x180019353  sub     rax, 1
0x180019357  jnz     short loc_18001934A
0x180019359  jmp     short loc_180019334
0x18001935b  lea     r8, [rsp+288h+Source]; Source
0x180019360  mov     rdx, r14; SizeInWords
0x180019363  mov     rcx, rdi; Destination
0x180019366  call    wcscat_s
0x18001936b  jmp     short loc_180019379
0x18001936d  call    cs:__imp__o__errno
0x180019373  mov     dword ptr [rax], 16h
0x180019379  lea     rdx, aPdb_3; ".pdb"
0x180019380  mov     rcx, rsi; unsigned __int16 *
0x180019383  call    ?extmatch@@YAHPEBG0@Z; extmatch(ushort const *,ushort const *)
0x180019388  mov     rcx, rsi; unsigned __int16 *
0x18001938b  test    eax, eax
0x18001938d  jz      short loc_1800193C5
0x18001938f  lea     rdi, [rbx+630h]
0x180019396  mov     rdx, rdi; struct _GUID *
0x180019399  lea     r8, [rbx+644h]; unsigned int *
0x1800193a0  call    ?diaGetPdbIndexInfo@@YAHPEBGPEAU_GUID@@PEAK@Z; diaGetPdbIndexInfo(ushort const *,_GUID *,ulong *)
0x1800193a5  test    eax, eax
0x1800193a7  jz      loc_1800192C1
0x1800193ad  cmp     [rbx+634h], bp
0x1800193b4  jnz     short loc_1800193BE
0x1800193b6  mov     ecx, [rdi]
0x1800193b8  mov     [rbx+640h], ecx
0x1800193be  mov     eax, 1
0x1800193c3  jmp     short loc_1800193CD
0x1800193c5  mov     rdx, rbx; struct SYMSRV_INDEX_INFOW *
0x1800193c8  call    ?ReadImageIndexInfo@@YAHPEBGPEAUSYMSRV_INDEX_INFOW@@@Z; ReadImageIndexInfo(ushort const *,SYMSRV_INDEX_INFOW *)
0x1800193cd  mov     rcx, [rsp+288h+var_28]
0x1800193d5  xor     rcx, rsp; StackCookie
0x1800193d8  call    __security_check_cookie
0x1800193dd  lea     r11, [rsp+288h+var_18]
0x1800193e5  mov     rbx, [r11+30h]
0x1800193e9  mov     rbp, [r11+38h]
0x1800193ed  mov     rsp, r11
0x1800193f0  pop     r14
0x1800193f2  pop     rdi
0x1800193f3  pop     rsi
0x1800193f4  retn
```
