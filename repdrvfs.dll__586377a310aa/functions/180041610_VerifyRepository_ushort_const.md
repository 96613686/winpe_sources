# VerifyRepository(ushort const *)

- ea: `0x180041610`
- end: `0x1800417f0`
- name: `?VerifyRepository@@YAJPEBG@Z`
- size: `480`
- prototype: `signed int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003d410`

## callees

- `0x1800012b8`
- `0x18003a550`
- `0x180040e24`
- `0x180041610`
- `0x1800417f8`
- `0x180041b68`
- `0x180041d28`
- `0x180041e38`
- `0x180041f30`
- `0x1800420ac`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800416a1`
- `wbemcomn!GetMemLogObject` at `0x180041705`
- `wbemcomn!GetMemLogObject` at `0x1800416a1`
- `wbemcomn!GetMemLogObject` at `0x180041705`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800416ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041710`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800416ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041710`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041658`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041664`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004167e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004167e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall VerifyRepository(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  signed int result; // eax
  int v4; // eax
  const unsigned __int16 *v5; // rcx
  int RepositoryDirectory; // ebx
  CMemoryLog *v7; // rax
  const unsigned __int16 *v8; // rcx
  int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  int v11; // ebx
  unsigned int v12; // edx
  const unsigned __int16 *v13; // rcx
  unsigned int v14; // edx
  bool v15; // [rsp+40h] [rbp-238h] BYREF
  unsigned int v16[3]; // [rsp+44h] [rbp-234h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( a1 )
  {
    FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    CloseHandle(FileW);
    v4 = PerformAllValidations(a1);
    goto LABEL_21;
  }
  RepositoryDirectory = GetRepositoryDirectory(Dst);
  if ( RepositoryDirectory >= 0 )
  {
    v15 = 0;
    v9 = QueryService(v5, &v15);
    if ( v9 >= 0 )
    {
      if ( !v15 )
      {
        v16[0] = -1;
        v11 = DisableService(v8, v16);
        if ( v11 >= 0 )
        {
          v11 = StopService(L"WinMgmt", v12);
          if ( v11 >= 0 )
            v11 = PerformAllValidations(Dst);
          EnableService(v13, v16[0]);
          StartServiceW(L"WinMgmt", v14);
        }
        goto LABEL_26;
      }
      v4 = VerifyRepositoryOnline(Dst);
LABEL_21:
      v11 = v4;
LABEL_26:
      if ( g_error && v11 >= 0 )
      {
        v11 = -2147023538;
        g_error = 0;
      }
      return v11;
    }
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_c47982387556333a241fa51fba0ef2c5_Traceguids,
        (unsigned int)v9);
    }
    return v9;
  }
  else
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, RepositoryDirectory);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_c47982387556333a241fa51fba0ef2c5_Traceguids,
        (unsigned int)RepositoryDirectory);
    }
    return RepositoryDirectory;
  }
}

```

## disassembly

```asm
0x180041610  push    rbx
0x180041612  sub     rsp, 270h
0x180041619  mov     rax, cs:__security_cookie
0x180041620  xor     rax, rsp
0x180041623  mov     [rsp+278h+var_18], rax
0x18004162b  mov     rbx, rcx
0x18004162e  test    rcx, rcx
0x180041631  jz      short loc_180041691
0x180041633  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x18004163c  mov     [rsp+278h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180041644  mov     [rsp+278h+dwCreationDisposition], 3; dwCreationDisposition
0x18004164c  xor     r9d, r9d; lpSecurityAttributes
0x18004164f  mov     edx, 80000000h; dwDesiredAccess
0x180041654  lea     r8d, [r9+7]; dwShareMode
0x180041658  call    cs:__imp_CreateFileW
0x18004165e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180041662  jnz     short loc_18004167B
0x180041664  call    cs:__imp_GetLastError
0x18004166a  test    eax, eax
0x18004166c  jle     short loc_180041676
0x18004166e  movzx   eax, ax
0x180041671  or      eax, 80070000h
0x180041676  jmp     loc_1800417D6
0x18004167b  mov     rcx, rax; hObject
0x18004167e  call    cs:__imp_CloseHandle
0x180041684  mov     rcx, rbx; unsigned __int16 *
0x180041687  call    ?PerformAllValidations@@YAJPEBG@Z; PerformAllValidations(ushort const *)
0x18004168c  jmp     loc_180041765
0x180041691  lea     rcx, [rsp+278h+Dst]; lpDst
0x180041696  call    ?GetRepositoryDirectory@@YAJQEAG@Z; GetRepositoryDirectory(ushort * const)
0x18004169b  mov     ebx, eax
0x18004169d  test    eax, eax
0x18004169f  jns     short loc_1800416F0
0x1800416a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800416a7  mov     edx, ebx
0x1800416a9  mov     rcx, rax
0x1800416ac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800416b2  lea     rax, WPP_GLOBAL_Control
0x1800416b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416c0  cmp     rcx, rax
0x1800416c3  jz      short loc_1800416E9
0x1800416c5  test    byte ptr [rcx+1Ch], 1
0x1800416c9  jz      short loc_1800416E9
0x1800416cb  cmp     byte ptr [rcx+19h], 2
0x1800416cf  jb      short loc_1800416E9
0x1800416d1  mov     edx, 0Ah
0x1800416d6  mov     r9d, ebx
0x1800416d9  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x1800416e0  mov     rcx, [rcx+10h]
0x1800416e4  call    WPP_SF_d
0x1800416e9  mov     eax, ebx
0x1800416eb  jmp     loc_1800417D6
0x1800416f0  mov     [rsp+278h+var_238], 0
0x1800416f5  lea     rdx, [rsp+278h+var_238]; bool *
0x1800416fa  call    ?QueryService@@YAJPEBGAEA_N@Z; QueryService(ushort const *,bool &)
0x1800416ff  mov     ebx, eax
0x180041701  test    eax, eax
0x180041703  jns     short loc_180041754
0x180041705  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004170b  mov     edx, ebx
0x18004170d  mov     rcx, rax
0x180041710  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041716  lea     rax, WPP_GLOBAL_Control
0x18004171d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041724  cmp     rcx, rax
0x180041727  jz      short loc_18004174D
0x180041729  test    byte ptr [rcx+1Ch], 1
0x18004172d  jz      short loc_18004174D
0x18004172f  cmp     byte ptr [rcx+19h], 2
0x180041733  jb      short loc_18004174D
0x180041735  mov     edx, 0Bh
0x18004173a  mov     r9d, ebx
0x18004173d  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180041744  mov     rcx, [rcx+10h]
0x180041748  call    WPP_SF_d
0x18004174d  mov     eax, ebx
0x18004174f  jmp     loc_1800417D6
0x180041754  cmp     [rsp+278h+var_238], 0
0x180041759  jz      short loc_180041769
0x18004175b  lea     rcx, [rsp+278h+Dst]; unsigned __int16 *
0x180041760  call    ?VerifyRepositoryOnline@@YAJPEBG@Z; VerifyRepositoryOnline(ushort const *)
0x180041765  mov     ebx, eax
0x180041767  jmp     short loc_1800417B4
0x180041769  mov     [rsp+278h+var_234], 0FFFFFFFFh
0x180041771  lea     rdx, [rsp+278h+var_234]; unsigned int *
0x180041776  call    ?DisableService@@YAJPEBGAEAK@Z; DisableService(ushort const *,ulong &)
0x18004177b  mov     ebx, eax
0x18004177d  test    eax, eax
0x18004177f  js      short loc_1800417B4
0x180041781  lea     rcx, ServiceName; "WinMgmt"
0x180041788  call    ?StopService@@YAJPEBGK@Z; StopService(ushort const *,ulong)
0x18004178d  mov     ebx, eax
0x18004178f  test    eax, eax
0x180041791  js      short loc_18004179F
0x180041793  lea     rcx, [rsp+278h+Dst]; unsigned __int16 *
0x180041798  call    ?PerformAllValidations@@YAJPEBG@Z; PerformAllValidations(ushort const *)
0x18004179d  mov     ebx, eax
0x18004179f  mov     edx, [rsp+278h+var_234]; unsigned int
0x1800417a3  call    ?EnableService@@YAJPEBGK@Z; EnableService(ushort const *,ulong)
0x1800417a8  lea     rcx, ServiceName; "WinMgmt"
0x1800417af  call    ?StartServiceW@@YAJPEBGK@Z; StartServiceW(ushort const *,ulong)
0x1800417b4  cmp     cs:?g_error@@3_NA, 0; bool g_error
0x1800417bb  jz      short loc_1800417CD
0x1800417bd  test    ebx, ebx
0x1800417bf  js      short loc_1800417CD
0x1800417c1  mov     ebx, 8007054Eh
0x1800417c6  mov     cs:?g_error@@3_NA, 0; bool g_error
0x1800417cd  mov     eax, ebx
0x1800417cf  jmp     short loc_1800417D6
0x1800417d1  mov     eax, 80041006h
0x1800417d6  mov     rcx, [rsp+278h+var_18]
0x1800417de  xor     rcx, rsp; StackCookie
0x1800417e1  call    __security_check_cookie
0x1800417e6  add     rsp, 270h
0x1800417ed  pop     rbx
0x1800417ee  retn
```
