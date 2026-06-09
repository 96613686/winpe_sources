# DockingProvider::Load(ushort const *,ushort const *)

- ea: `0x180015d24`
- end: `0x180015ff2`
- name: `?Load@DockingProvider@@QEAAJPEBG0@Z`
- size: `718`
- prototype: `__int64 __fastcall(DockingProvider *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180015700`

## callees

- `0x18000c348`
- `0x18000c398`
- `0x180010700`
- `0x180015d24`
- `0x1800177f0`
- `0x180017928`
- `0x180017af4`
- `0x18001f010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180015d95`
- `msvcrt!wcsncpy_s` at `0x180015d95`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015dba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015dba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015da2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015da2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ddc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015dc9`

## pseudocode

```c
__int64 __fastcall DockingProvider::Load(DockingProvider *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  int ExportByName; // edi
  int v9; // edx
  int v10; // r8d
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 (__fastcall *v15)(__int64 *, char *); // rax
  int v16; // eax
  __int64 v17; // r8
  void (__fastcall *v18)(char *); // rax
  void *v19; // [rsp+60h] [rbp+8h] BYREF
  __int64 v20; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
  }
  wcsncpy_s((wchar_t *)this + 108, 0x104u, a2, 0x104u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_QWORD *)this + 6) )
  {
    ++*((_DWORD *)this + 14);
  }
  else
  {
    Library = LoadLibraryExW(a3, 0, 0x800u);
    *((_QWORD *)this + 6) = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      ExportByName = 774;
      if ( LastError )
        ExportByName = LastError;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (_DWORD)this, ExportByName, (__int64)a3);
      }
      goto LABEL_13;
    }
    *((_DWORD *)this + 14) = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v19 = 0;
  ExportByName = DLL::GetExportByName((LPCRITICAL_SECTION)((char *)this + 8), "InitializeDockingProvider", &v19);
  if ( ExportByName )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 12;
LABEL_23:
      WPP_SF_qD(v12[2], v13, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, ExportByName);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  *((_QWORD *)this + 8) = v19;
  v14 = DLL::GetExportByName((LPCRITICAL_SECTION)((char *)this + 8), "ShutdownDockingProvider", &v19);
  ExportByName = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, v14);
    }
    goto LABEL_13;
  }
  *((_QWORD *)this + 9) = v19;
  v15 = (__int64 (__fastcall *)(__int64 *, char *))*((_QWORD *)this + 8);
  v20 = 0;
  v16 = v15(&v20, (char *)this + 88);
  ExportByName = v16;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qID(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v17, this, v20, v16);
    v12 = WPP_GLOBAL_Control;
  }
  if ( ExportByName )
  {
    if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) && (*((_BYTE *)v12 + 28) & 1) != 0 )
    {
      v13 = 15;
      goto LABEL_23;
    }
LABEL_13:
    if ( ExportByName > 0 )
      return (unsigned __int16)ExportByName | 0x80070000;
    return (unsigned int)ExportByName;
  }
  if ( (_WORD)v20 )
    return 0;
  if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_qDD(v12[2], WORD1(v20), v20, this, (unsigned __int16)v20, WORD1(v20));
  v18 = (void (__fastcall *)(char *))*((_QWORD *)this + 9);
  *((_DWORD *)this + 20) = 0;
  v18((char *)this + 88);
  return 2147943032LL;
}

```

## disassembly

```asm
0x180015d24  mov     [rsp+arg_8], rbx
0x180015d29  push    rbp
0x180015d2a  push    rsi
0x180015d2b  push    rdi
0x180015d2c  push    r12
0x180015d2e  push    r14
0x180015d30  sub     rsp, 30h
0x180015d34  mov     rbp, r8
0x180015d37  mov     rdi, rdx
0x180015d3a  mov     rbx, rcx
0x180015d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d44  lea     r12, WPP_GLOBAL_Control
0x180015d4b  mov     r14d, 1
0x180015d51  cmp     rcx, r12
0x180015d54  jz      short loc_180015D83
0x180015d56  cmp     byte ptr [rcx+19h], 3
0x180015d5a  jb      short loc_180015D83
0x180015d5c  test    [rcx+1Ch], r14b
0x180015d60  jz      short loc_180015D83
0x180015d62  mov     rcx, [rcx+10h]; LoggerHandle
0x180015d66  lea     edx, [r14+9]
0x180015d6a  mov     [rsp+58h+var_30], r8; __int64
0x180015d6f  mov     r9, rbx
0x180015d72  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180015d79  mov     [rsp+58h+var_38], rdi; __int64
0x180015d7e  call    WPP_SF_qSS
0x180015d83  mov     edx, 104h; SizeInWords
0x180015d88  lea     rcx, [rbx+0D8h]; Destination
0x180015d8f  mov     r9d, edx; MaxCount
0x180015d92  mov     r8, rdi; Source
0x180015d95  call    cs:__imp_wcsncpy_s
0x180015d9b  lea     rsi, [rbx+8]
0x180015d9f  mov     rcx, rsi; lpCriticalSection
0x180015da2  call    cs:__imp_EnterCriticalSection
0x180015da8  cmp     qword ptr [rsi+28h], 0
0x180015dad  jnz     short loc_180015E29
0x180015daf  xor     edx, edx; hFile
0x180015db1  mov     r8d, 800h; dwFlags
0x180015db7  mov     rcx, rbp; lpLibFileName
0x180015dba  call    cs:__imp_LoadLibraryExW
0x180015dc0  mov     [rbx+30h], rax
0x180015dc4  test    rax, rax
0x180015dc7  jnz     short loc_180015E23
0x180015dc9  call    cs:__imp_GetLastError
0x180015dcf  mov     edi, 306h
0x180015dd4  mov     rcx, rsi; lpCriticalSection
0x180015dd7  test    eax, eax
0x180015dd9  cmovnz  edi, eax
0x180015ddc  call    cs:__imp_LeaveCriticalSection
0x180015de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015de9  cmp     rcx, r12
0x180015dec  jz      short loc_180015E0F
0x180015dee  cmp     [rcx+19h], r14b
0x180015df2  jb      short loc_180015E0F
0x180015df4  test    [rcx+1Ch], r14b
0x180015df8  jz      short loc_180015E0F
0x180015dfa  mov     rcx, [rcx+10h]
0x180015dfe  mov     r9, rbx
0x180015e01  mov     [rsp+58h+var_30], rbp
0x180015e06  mov     dword ptr [rsp+58h+var_38], edi
0x180015e0a  call    WPP_SF_qDS
0x180015e0f  test    edi, edi
0x180015e11  jle     short loc_180015E1C
0x180015e13  movzx   edi, di
0x180015e16  or      edi, 80070000h
0x180015e1c  mov     eax, edi
0x180015e1e  jmp     loc_180015FE1
0x180015e23  mov     [rbx+38h], r14d
0x180015e27  jmp     short loc_180015E2D
0x180015e29  add     [rbx+38h], r14d
0x180015e2d  mov     rcx, rsi; lpCriticalSection
0x180015e30  call    cs:__imp_LeaveCriticalSection
0x180015e36  lea     r8, [rsp+58h+arg_0]; void **
0x180015e3b  mov     [rsp+58h+arg_0], 0
0x180015e44  lea     rdx, aInitializedock; "InitializeDockingProvider"
0x180015e4b  mov     rcx, rsi; lpCriticalSection
0x180015e4e  call    ?GetExportByName@DLL@@QEAAKPEBDPEAPEAX@Z; DLL::GetExportByName(char const *,void * *)
0x180015e53  mov     edi, eax
0x180015e55  test    eax, eax
0x180015e57  jz      short loc_180015E8F
0x180015e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e60  cmp     rcx, r12
0x180015e63  jz      short loc_180015E0F
0x180015e65  cmp     [rcx+19h], r14b
0x180015e69  jb      short loc_180015E0F
0x180015e6b  test    [rcx+1Ch], r14b
0x180015e6f  jz      short loc_180015E0F
0x180015e71  mov     edx, 0Ch
0x180015e76  mov     rcx, [rcx+10h]
0x180015e7a  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180015e81  mov     r9, rbx
0x180015e84  mov     dword ptr [rsp+58h+var_38], edi
0x180015e88  call    WPP_SF_qD
0x180015e8d  jmp     short loc_180015E0F
0x180015e8f  mov     rax, [rsp+58h+arg_0]
0x180015e94  lea     r8, [rsp+58h+arg_0]; void **
0x180015e99  lea     rdx, aShutdowndockin; "ShutdownDockingProvider"
0x180015ea0  mov     [rbx+40h], rax
0x180015ea4  mov     rcx, rsi; lpCriticalSection
0x180015ea7  call    ?GetExportByName@DLL@@QEAAKPEBDPEAPEAX@Z; DLL::GetExportByName(char const *,void * *)
0x180015eac  mov     edi, eax
0x180015eae  test    eax, eax
0x180015eb0  jz      short loc_180015EF7
0x180015eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015eb9  cmp     rcx, r12
0x180015ebc  jz      loc_180015E0F
0x180015ec2  cmp     [rcx+19h], r14b
0x180015ec6  jb      loc_180015E0F
0x180015ecc  test    [rcx+1Ch], r14b
0x180015ed0  jz      loc_180015E0F
0x180015ed6  mov     rcx, [rcx+10h]
0x180015eda  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180015ee1  mov     edx, 0Dh
0x180015ee6  mov     dword ptr [rsp+58h+var_38], eax
0x180015eea  mov     r9, rbx
0x180015eed  call    WPP_SF_qD
0x180015ef2  jmp     loc_180015E0F
0x180015ef7  mov     rax, [rsp+58h+arg_0]
0x180015efc  lea     rdx, [rbx+58h]
0x180015f00  mov     [rbx+48h], rax
0x180015f04  lea     rcx, [rsp+58h+arg_18]
0x180015f09  mov     rax, [rbx+40h]
0x180015f0d  mov     [rsp+58h+arg_18], 0
0x180015f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f1b  mov     edi, eax
0x180015f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f24  cmp     rcx, r12
0x180015f27  jz      short loc_180015F5B
0x180015f29  cmp     byte ptr [rcx+19h], 3
0x180015f2d  jb      short loc_180015F5B
0x180015f2f  test    [rcx+1Ch], r14b
0x180015f33  jz      short loc_180015F5B
0x180015f35  mov     rcx, [rcx+10h]
0x180015f39  mov     edx, 0Eh
0x180015f3e  mov     dword ptr [rsp+58h+var_30], eax
0x180015f42  mov     r9, rbx
0x180015f45  mov     rax, [rsp+58h+arg_18]
0x180015f4a  mov     [rsp+58h+var_38], rax
0x180015f4f  call    WPP_SF_qID
0x180015f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f5b  test    edi, edi
0x180015f5d  jz      short loc_180015F86
0x180015f5f  cmp     rcx, r12
0x180015f62  jz      loc_180015E0F
0x180015f68  cmp     [rcx+19h], r14b
0x180015f6c  jb      loc_180015E0F
0x180015f72  test    [rcx+1Ch], r14b
0x180015f76  jz      loc_180015E0F
0x180015f7c  mov     edx, 0Fh
0x180015f81  jmp     loc_180015E76
0x180015f86  mov     r8, [rsp+58h+arg_18]
0x180015f8b  cmp     r8w, r14w
0x180015f8f  jnb     short loc_180015FDF
0x180015f91  cmp     rcx, r12
0x180015f94  jz      short loc_180015FC4
0x180015f96  cmp     [rcx+19h], r14b
0x180015f9a  jb      short loc_180015FC4
0x180015f9c  test    [rcx+1Ch], r14b
0x180015fa0  jz      short loc_180015FC4
0x180015fa2  mov     rcx, [rcx+10h]
0x180015fa6  mov     rax, r8
0x180015fa9  shr     rax, 10h
0x180015fad  mov     r9, rbx
0x180015fb0  movzx   edx, ax
0x180015fb3  movzx   eax, r8w
0x180015fb7  mov     dword ptr [rsp+58h+var_30], edx
0x180015fbb  mov     dword ptr [rsp+58h+var_38], eax
0x180015fbf  call    WPP_SF_qDD
0x180015fc4  mov     rax, [rbx+48h]
0x180015fc8  lea     rcx, [rbx+58h]
0x180015fcc  mov     dword ptr [rbx+50h], 0
0x180015fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd8  mov     eax, 80070278h
0x180015fdd  jmp     short loc_180015FE1
0x180015fdf  xor     eax, eax
0x180015fe1  mov     rbx, [rsp+58h+arg_8]
0x180015fe6  add     rsp, 30h
0x180015fea  pop     r14
0x180015fec  pop     r12
0x180015fee  pop     rdi
0x180015fef  pop     rsi
0x180015ff0  pop     rbp
0x180015ff1  retn
```
