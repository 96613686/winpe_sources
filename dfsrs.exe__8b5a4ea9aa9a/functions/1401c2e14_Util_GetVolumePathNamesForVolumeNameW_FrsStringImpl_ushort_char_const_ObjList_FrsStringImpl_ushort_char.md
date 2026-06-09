# Util::GetVolumePathNamesForVolumeNameW(FrsStringImpl<ushort,char> const &,ObjList<FrsStringImpl<ushort,char>> &)

- ea: `0x1401c2e14`
- end: `0x1401c3066`
- name: `?GetVolumePathNamesForVolumeNameW@Util@@YAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAV?$ObjList@V?$FrsStringImpl@GD@@@@@Z`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140041888`

## callees

- `0x14000ee94`
- `0x14001cfa0`
- `0x14002c548`
- `0x14004691c`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b3af8`
- `0x1401b9494`
- `0x1401c2e14`
- `0x1401c32d8`
- `0x1401c3480`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401c2ebd`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401c2f3c`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401c2ebd`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1401c2f3c`
- `KERNEL32!GetLastError` at `0x1401c2edc`
- `KERNEL32!GetLastError` at `0x1401c2edc`
- `KERNEL32!GetCurrentThreadId` at `0x1401c2e69`
- `KERNEL32!GetCurrentThreadId` at `0x1401c2f4d`
- `KERNEL32!GetCurrentThreadId` at `0x1401c2ff0`
- `KERNEL32!GetCurrentThreadId` at `0x1401c2e69`
- `KERNEL32!GetCurrentThreadId` at `0x1401c2f4d`
- `KERNEL32!GetCurrentThreadId` at `0x1401c2ff0`

## string_xrefs

- `0x1401c2e57`: `Util::GetVolumePathNamesForVolumeNameW`
- `0x1401c2ecc`: `Util::GetVolumePathNamesForVolumeNameW`
- `0x1401c300d`: `Util::GetVolumePathNamesForVolumeNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Util::GetVolumePathNamesForVolumeNameW(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  _WORD *v4; // rbx
  DWORD v5; // eax
  __int64 v6; // rcx
  BOOL VolumePathNamesForVolumeNameW; // r14d
  DWORD LastError; // esi
  _WORD *v9; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // r12
  __int64 v13; // rax
  unsigned __int64 v14; // rdx
  int v15; // esi
  DWORD v16; // eax
  __int64 v17; // rcx
  _BYTE v19[16]; // [rsp+50h] [rbp-10h] BYREF
  DWORD cchBufferLength; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int64 v21; // [rsp+B0h] [rbp+50h] BYREF
  _WORD *v22; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  cchBufferLength = 0;
  v4 = 0;
  v22 = 0;
  v21 = a2 + 8;
  std::vector<FrsStringImpl<unsigned short,char>>::clear(a2 + 8);
  if ( (unsigned int)Util::VolumeNameIsValid(a1)
    || (v5 = GetCurrentThreadId(),
        (v3 = FrsStatusList::PushNewError(
                v6,
                87,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\fsutil.cpp",
                "Util::GetVolumePathNamesForVolumeNameW",
                446,
                v5,
                0)) == 0) )
  {
    VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                      (LPCWSTR)(*(_QWORD *)a1 + 18LL),
                                      0,
                                      cchBufferLength,
                                      &cchBufferLength);
    do
    {
      if ( VolumePathNamesForVolumeNameW )
        break;
      LastError = GetLastError();
      if ( LastError == 234 )
      {
        v9 = operator_new(saturated_mul(cchBufferLength, 2u));
        if ( v4 != v9 )
        {
          if ( v4 )
            operator delete[](v4);
          v4 = v9;
          v22 = v9;
        }
        VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(
                                          (LPCWSTR)(*(_QWORD *)a1 + 18LL),
                                          v4,
                                          cchBufferLength,
                                          &cchBufferLength);
      }
      else
      {
        CurrentThreadId = GetCurrentThreadId();
        v3 = FrsStatusList::PushNewError(
               v11,
               LastError,
               0,
               1,
               "base\\fs\\remotefs\\frs\\src\\util\\fsutil.cpp",
               "Util::GetVolumePathNamesForVolumeNameW",
               492,
               CurrentThreadId,
               0);
      }
    }
    while ( !v3 );
    v12 = v21;
    while ( !v3 && *v4 )
    {
      v13 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v19, v4);
      std::vector<FrsStringImpl<unsigned short,char>>::push_back(v12, v13);
      FrsStringImpl<char,unsigned short>::ReleaseBody(v19);
      v21 = 0;
      v15 = StringCchLengthW(v4, v14, &v21);
      if ( v15 < 0 )
      {
        v16 = GetCurrentThreadId();
        v3 = FrsStatusList::PushNewError(
               v17,
               (unsigned int)v15,
               0,
               4,
               "base\\fs\\remotefs\\frs\\src\\util\\fsutil.cpp",
               "Util::GetVolumePathNamesForVolumeNameW",
               542,
               v16,
               0);
      }
      else
      {
        v4 += v21 + 1;
      }
    }
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v22);
  return v3;
}

```

## disassembly

```asm
0x1401c2e14  mov     [rsp-38h+arg_0], rbx
0x1401c2e19  push    rbp
0x1401c2e1a  push    rsi
0x1401c2e1b  push    rdi
0x1401c2e1c  push    r12
0x1401c2e1e  push    r13
0x1401c2e20  push    r14
0x1401c2e22  push    r15
0x1401c2e24  mov     rbp, rsp
0x1401c2e27  sub     rsp, 60h
0x1401c2e2b  mov     r15, rcx
0x1401c2e2e  xor     r13d, r13d
0x1401c2e31  mov     edi, r13d
0x1401c2e34  mov     [rbp+cchBufferLength], r13d
0x1401c2e38  mov     ebx, r13d
0x1401c2e3b  mov     [rbp+arg_18], rbx
0x1401c2e3f  lea     r12, [rdx+8]
0x1401c2e43  mov     [rbp+arg_10], r12
0x1401c2e47  mov     rcx, r12
0x1401c2e4a  call    ?clear@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXXZ; std::vector<FrsStringImpl<ushort,char>>::clear(void)
0x1401c2e4f  mov     rcx, r15
0x1401c2e52  call    ?VolumeNameIsValid@Util@@YAHAEBV?$FrsStringImpl@GD@@@Z; Util::VolumeNameIsValid(FrsStringImpl<ushort,char> const &)
0x1401c2e57  lea     rsi, aUtilGetvolumep; "Util::GetVolumePathNamesForVolumeNameW"
0x1401c2e5e  lea     r14, aBaseFsRemotefs_82; "base\\fs\\remotefs\\frs\\src\\util\\fsu"...
0x1401c2e65  test    eax, eax
0x1401c2e67  jnz     short loc_1401C2EAC
0x1401c2e69  call    cs:__imp_GetCurrentThreadId
0x1401c2e70  nop     dword ptr [rax+rax+00h]
0x1401c2e75  mov     [rsp+60h+var_20], r13
0x1401c2e7a  mov     [rsp+60h+var_28], eax
0x1401c2e7e  mov     [rsp+60h+var_30], 1BEh
0x1401c2e86  mov     [rsp+60h+var_38], rsi
0x1401c2e8b  mov     [rsp+60h+var_40], r14
0x1401c2e90  lea     r9d, [r13+1]
0x1401c2e94  xor     r8d, r8d
0x1401c2e97  lea     edx, [r13+57h]
0x1401c2e9b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c2ea0  mov     rdi, rax
0x1401c2ea3  test    rax, rax
0x1401c2ea6  jnz     loc_1401C3041
0x1401c2eac  mov     rcx, [r15]
0x1401c2eaf  add     rcx, 12h; lpszVolumeName
0x1401c2eb3  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x1401c2eb7  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x1401c2ebb  xor     edx, edx; lpszVolumePathNames
0x1401c2ebd  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1401c2ec4  nop     dword ptr [rax+rax+00h]
0x1401c2ec9  mov     r14d, eax
0x1401c2ecc  lea     r12, aUtilGetvolumep; "Util::GetVolumePathNamesForVolumeNameW"
0x1401c2ed3  test    r14d, r14d
0x1401c2ed6  jnz     loc_1401C2F97
0x1401c2edc  call    cs:__imp_GetLastError
0x1401c2ee3  nop     dword ptr [rax+rax+00h]
0x1401c2ee8  mov     esi, eax
0x1401c2eea  cmp     eax, 0EAh
0x1401c2eef  jnz     short loc_1401C2F4D
0x1401c2ef1  mov     edx, [rbp+cchBufferLength]
0x1401c2ef4  lea     eax, [r14+2]
0x1401c2ef8  mul     rdx
0x1401c2efb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401c2f02  cmovo   rax, rcx
0x1401c2f06  mov     rcx, rax; unsigned __int64
0x1401c2f09  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c2f0e  mov     rsi, rax
0x1401c2f11  cmp     rbx, rax
0x1401c2f14  jz      short loc_1401C2F2A
0x1401c2f16  test    rbx, rbx
0x1401c2f19  jz      short loc_1401C2F23
0x1401c2f1b  mov     rcx, rbx; Block
0x1401c2f1e  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c2f23  mov     rbx, rsi
0x1401c2f26  mov     [rbp+arg_18], rbx
0x1401c2f2a  mov     rcx, [r15]
0x1401c2f2d  add     rcx, 12h; lpszVolumeName
0x1401c2f31  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x1401c2f35  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x1401c2f39  mov     rdx, rbx; lpszVolumePathNames
0x1401c2f3c  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1401c2f43  nop     dword ptr [rax+rax+00h]
0x1401c2f48  mov     r14d, eax
0x1401c2f4b  jmp     short loc_1401C2F8E
0x1401c2f4d  call    cs:__imp_GetCurrentThreadId
0x1401c2f54  nop     dword ptr [rax+rax+00h]
0x1401c2f59  mov     [rsp+60h+var_20], r13
0x1401c2f5e  mov     [rsp+60h+var_28], eax
0x1401c2f62  mov     [rsp+60h+var_30], 1ECh
0x1401c2f6a  mov     [rsp+60h+var_38], r12
0x1401c2f6f  lea     rax, aBaseFsRemotefs_82; "base\\fs\\remotefs\\frs\\src\\util\\fsu"...
0x1401c2f76  mov     [rsp+60h+var_40], rax
0x1401c2f7b  mov     r9d, 1
0x1401c2f81  xor     r8d, r8d
0x1401c2f84  mov     edx, esi
0x1401c2f86  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c2f8b  mov     rdi, rax
0x1401c2f8e  test    rdi, rdi
0x1401c2f91  jz      loc_1401C2ED3
0x1401c2f97  mov     r12, [rbp+arg_10]
0x1401c2f9b  jmp     loc_1401C3038
0x1401c2fa0  cmp     [rbx], r13w
0x1401c2fa4  jz      loc_1401C3041
0x1401c2faa  mov     rdx, rbx
0x1401c2fad  lea     rcx, [rbp+var_10]
0x1401c2fb1  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401c2fb6  nop
0x1401c2fb7  mov     rdx, rax
0x1401c2fba  mov     rcx, r12
0x1401c2fbd  call    ?push_back@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXAEBV?$FrsStringImpl@GD@@@Z; std::vector<FrsStringImpl<ushort,char>>::push_back(FrsStringImpl<ushort,char> const &)
0x1401c2fc2  nop
0x1401c2fc3  lea     rcx, [rbp+var_10]
0x1401c2fc7  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401c2fcc  mov     [rbp+arg_10], r13
0x1401c2fd0  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x1401c2fd4  mov     rcx, rbx; unsigned __int16 *
0x1401c2fd7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1401c2fdc  mov     esi, eax
0x1401c2fde  test    eax, eax
0x1401c2fe0  js      short loc_1401C2FF0
0x1401c2fe2  mov     rax, [rbp+arg_10]
0x1401c2fe6  lea     rbx, [rbx+rax*2]
0x1401c2fea  add     rbx, 2
0x1401c2fee  jmp     short loc_1401C3038
0x1401c2ff0  call    cs:__imp_GetCurrentThreadId
0x1401c2ff7  nop     dword ptr [rax+rax+00h]
0x1401c2ffc  mov     [rsp+60h+var_20], r13
0x1401c3001  mov     [rsp+60h+var_28], eax
0x1401c3005  mov     [rsp+60h+var_30], 21Eh
0x1401c300d  lea     rax, aUtilGetvolumep; "Util::GetVolumePathNamesForVolumeNameW"
0x1401c3014  mov     [rsp+60h+var_38], rax
0x1401c3019  lea     rax, aBaseFsRemotefs_82; "base\\fs\\remotefs\\frs\\src\\util\\fsu"...
0x1401c3020  mov     [rsp+60h+var_40], rax
0x1401c3025  mov     r9d, 4
0x1401c302b  xor     r8d, r8d
0x1401c302e  mov     edx, esi
0x1401c3030  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c3035  mov     rdi, rax
0x1401c3038  test    rdi, rdi
0x1401c303b  jz      loc_1401C2FA0
0x1401c3041  lea     rcx, [rbp+arg_18]
0x1401c3045  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401c304a  mov     rax, rdi
0x1401c304d  mov     rbx, [rsp+60h+arg_0]
0x1401c3055  add     rsp, 60h
0x1401c3059  pop     r15
0x1401c305b  pop     r14
0x1401c305d  pop     r13
0x1401c305f  pop     r12
0x1401c3061  pop     rdi
0x1401c3062  pop     rsi
0x1401c3063  pop     rbp
0x1401c3064  retn
```
