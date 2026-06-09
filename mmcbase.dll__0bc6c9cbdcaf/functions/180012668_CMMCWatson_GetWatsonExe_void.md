# CMMCWatson::GetWatsonExe(void)

- ea: `0x180012668`
- end: `0x1800127a4`
- name: `?GetWatsonExe@CMMCWatson@@AEAA_NXZ`
- size: `316`
- prototype: `bool __fastcall(CMMCWatson *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180012834`

## callees

- `0x18000bd34`
- `0x180012668`
- `0x180012f0c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800126e2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001272e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800126e2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001272e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001268a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001268a`

## pseudocode

```c
bool __fastcall CMMCWatson::GetWatsonExe(CMMCWatson *this)
{
  unsigned __int16 *v1; // rdi
  UINT SystemDirectoryW; // eax
  __int64 v4; // rsi
  unsigned __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  DWORD FileAttributesW; // eax
  unsigned __int64 v9; // rdx
  DWORD v10; // eax

  v1 = (unsigned __int16 *)((char *)this + 34);
  *((_BYTE *)this + 32) = 0;
  SystemDirectoryW = GetSystemDirectoryW((LPWSTR)this + 17, 0x104u);
  v4 = SystemDirectoryW;
  v5 = SystemDirectoryW - 1;
  if ( (unsigned int)v5 > 0x103 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v7 = 41;
      goto LABEL_21;
    }
    return *((_BYTE *)this + 32);
  }
  if ( (int)StringCchCatW(v1, v5, L"\\dwwin.exe") < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v7 = 42;
LABEL_21:
      WPP_SF_(*(_QWORD *)(v6 + 16), v7, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
      return *((_BYTE *)this + 32);
    }
    return *((_BYTE *)this + 32);
  }
  FileAttributesW = GetFileAttributesW(v1);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
  {
LABEL_14:
    *((_BYTE *)this + 32) = 1;
    return *((_BYTE *)this + 32);
  }
  *((_WORD *)this + v4 + 17) = 0;
  if ( (int)StringCchCatW(v1, v9, L"\\dw20.exe") >= 0 )
  {
    v10 = GetFileAttributesW(v1);
    if ( v10 == -1 || (v10 & 0x10) != 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v7 = 44;
        goto LABEL_21;
      }
      return *((_BYTE *)this + 32);
    }
    goto LABEL_14;
  }
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v7 = 43;
    goto LABEL_21;
  }
  return *((_BYTE *)this + 32);
}

```

## disassembly

```asm
0x180012668  mov     [rsp+arg_0], rbx
0x18001266d  mov     [rsp+arg_8], rsi
0x180012672  push    rdi
0x180012673  sub     rsp, 20h
0x180012677  lea     rdi, [rcx+22h]
0x18001267b  mov     byte ptr [rcx+20h], 0
0x18001267f  mov     rbx, rcx
0x180012682  mov     edx, 104h; uSize
0x180012687  mov     rcx, rdi; lpBuffer
0x18001268a  call    cs:__imp_GetSystemDirectoryW
0x180012690  mov     esi, eax
0x180012692  lea     edx, [rsi-1]; unsigned __int64
0x180012695  cmp     edx, 103h
0x18001269b  ja      loc_180012763
0x1800126a1  lea     r8, aDwwinExe; "\\dwwin.exe"
0x1800126a8  mov     rcx, rdi; unsigned __int16 *
0x1800126ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800126b0  test    eax, eax
0x1800126b2  jns     short loc_1800126DF
0x1800126b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126bb  lea     rax, WPP_GLOBAL_Control
0x1800126c2  cmp     rcx, rax
0x1800126c5  jz      loc_180012791
0x1800126cb  cmp     byte ptr [rcx+19h], 2
0x1800126cf  jb      loc_180012791
0x1800126d5  mov     edx, 2Ah ; '*'
0x1800126da  jmp     loc_180012781
0x1800126df  mov     rcx, rdi; lpFileName
0x1800126e2  call    cs:__imp_GetFileAttributesW
0x1800126e8  cmp     eax, 0FFFFFFFFh
0x1800126eb  jz      short loc_1800126F1
0x1800126ed  test    al, 10h
0x1800126ef  jz      short loc_18001273D
0x1800126f1  xor     eax, eax
0x1800126f3  lea     r8, aDw20Exe; "\\dw20.exe"
0x1800126fa  mov     rcx, rdi; unsigned __int16 *
0x1800126fd  mov     [rbx+rsi*2+22h], ax
0x180012702  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012707  test    eax, eax
0x180012709  jns     short loc_18001272B
0x18001270b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012712  lea     rax, WPP_GLOBAL_Control
0x180012719  cmp     rcx, rax
0x18001271c  jz      short loc_180012791
0x18001271e  cmp     byte ptr [rcx+19h], 2
0x180012722  jb      short loc_180012791
0x180012724  mov     edx, 2Bh ; '+'
0x180012729  jmp     short loc_180012781
0x18001272b  mov     rcx, rdi; lpFileName
0x18001272e  call    cs:__imp_GetFileAttributesW
0x180012734  cmp     eax, 0FFFFFFFFh
0x180012737  jz      short loc_180012743
0x180012739  test    al, 10h
0x18001273b  jnz     short loc_180012743
0x18001273d  mov     byte ptr [rbx+20h], 1
0x180012741  jmp     short loc_180012791
0x180012743  mov     rcx, cs:WPP_GLOBAL_Control
0x18001274a  lea     rax, WPP_GLOBAL_Control
0x180012751  cmp     rcx, rax
0x180012754  jz      short loc_180012791
0x180012756  cmp     byte ptr [rcx+19h], 2
0x18001275a  jb      short loc_180012791
0x18001275c  mov     edx, 2Ch ; ','
0x180012761  jmp     short loc_180012781
0x180012763  mov     rcx, cs:WPP_GLOBAL_Control
0x18001276a  lea     rax, WPP_GLOBAL_Control
0x180012771  cmp     rcx, rax
0x180012774  jz      short loc_180012791
0x180012776  cmp     byte ptr [rcx+19h], 2
0x18001277a  jb      short loc_180012791
0x18001277c  mov     edx, 29h ; ')'
0x180012781  mov     rcx, [rcx+10h]
0x180012785  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x18001278c  call    WPP_SF_
0x180012791  mov     al, [rbx+20h]
0x180012794  mov     rbx, [rsp+28h+arg_0]
0x180012799  mov     rsi, [rsp+28h+arg_8]
0x18001279e  add     rsp, 20h
0x1800127a2  pop     rdi
0x1800127a3  retn
```
