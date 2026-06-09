# CMvExtensionKey::GetExtensionKeys(CfgMgrHelper *,IMVKey * *,ulong *)

- ea: `0x180014d68`
- end: `0x180015044`
- name: `?GetExtensionKeys@CMvExtensionKey@@QEBAJPEAVCfgMgrHelper@@PEAPEAUIMVKey@@PEAK@Z`
- size: `732`
- prototype: `int __fastcall(CMvExtensionKey *this, LPVOID *, struct IMVKey **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180013e50`

## callees

- `0x1800018fc`
- `0x1800076a4`
- `0x18001192c`
- `0x180014d68`
- `0x180015270`
- `0x180036414`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014eb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014f92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014eb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014f92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015010`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014e4c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014e4c`

## string_xrefs

- `0x180014edb`: `Extension handler`
- `0x180014f43`: `Extension handler`
- `0x180014dbe`: `onecoreuap\admin\prov\multivariant\handlers\extension\extensionkey.cpp`
- `0x180014fde`: `onecoreuap\admin\prov\multivariant\handlers\extension\extensionkey.cpp`
- `0x180015024`: `onecoreuap\admin\prov\multivariant\handlers\extension\extensionkey.cpp`

## pseudocode

```c
int __fastcall CMvExtensionKey::GetExtensionKeys(
        CMvExtensionKey *this,
        LPVOID *a2,
        struct IMVKey **a3,
        unsigned int *a4)
{
  LPVOID *v5; // rdi
  unsigned int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v11; // r12
  __int64 v12; // r14
  __int64 v13; // rcx
  unsigned int ValueW; // eax
  unsigned __int16 *v15; // rcx
  signed int v16; // edi
  __int64 v17; // r8
  __int64 v18; // r9
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // edi
  struct IMVKey *v24; // rcx
  void *v25; // rbx
  bool v26; // zf
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpValue; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID *p_lpMem; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-98h] BYREF
  char v37; // [rsp+70h] [rbp-90h]
  LPCWSTR v38; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v39; // [rsp+80h] [rbp-80h] BYREF
  struct IMVKey **v40; // [rsp+88h] [rbp-78h]
  struct CfgMgrHelper *v41; // [rsp+90h] [rbp-70h]
  OLECHAR psz[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v40 = a3;
  v5 = a2;
  v41 = (struct CfgMgrHelper *)a2;
  v7 = *((_DWORD *)this + 154);
  if ( *a4 >= v7 )
  {
    v11 = 0;
    v12 = 0;
    if ( !v7 )
    {
LABEL_18:
      *a4 = v11;
      return 0;
    }
    while ( 1 )
    {
      lpValue = 0;
      v13 = *(_QWORD *)(*((_QWORD *)this + 76) + 8 * v12);
      v8 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v13 + 40LL))(v13, &lpValue);
      if ( v8 < 0 )
      {
        v9 = 346;
        goto LABEL_3;
      }
      pcbData = 522;
      ValueW = RegGetValueW(*((HKEY *)this + 78), 0, lpValue, 2u, 0, psz, &pcbData);
      if ( ValueW )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x15F,
                 (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\extension\\extensionkey.cpp",
                 (const char *)ValueW,
                 pdwType);
      lpMem = 0;
      p_lpMem = &lpMem;
      v36 = 0;
      v37 = 1;
      v16 = CfgMgrHelper::QueryNodeValue(v5, psz, &v36, &v32);
      if ( v37 )
      {
        v19 = *p_lpMem;
        v15 = v36;
        *p_lpMem = v36;
        if ( v19 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v19);
        }
      }
      if ( v16 >= 0 )
      {
        v21 = *(_QWORD *)(*((_QWORD *)this + 76) + 8 * v12);
        v22 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v21 + 32LL))(v21, lpMem);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x173,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\extension\\extensionkey.cpp",
            (const char *)(unsigned int)v22,
            pdwType);
          v28 = lpMem;
          lpMem = 0;
          if ( v28 )
          {
            v29 = GetProcessHeap();
            HeapFree(v29, 0, v28);
          }
          return v23;
        }
        LogHandlerKeysReturned(L"Extension handler", 0, lpValue, (const unsigned __int16 *)lpMem);
        v24 = *(struct IMVKey **)(*((_QWORD *)this + 76) + 8 * v12);
        v40[v11] = v24;
        (*(void (__fastcall **)(struct IMVKey *))(*(_QWORD *)v24 + 8LL))(v24);
        v11 = (unsigned int)(v11 + 1);
      }
      else if ( (unsigned int)dword_180052170 > 2 )
      {
        v32 = v16;
        v38 = lpValue;
        v39 = L"Extension handler";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v15,
          (__int64)byte_18004960D,
          v17,
          v18,
          &v39,
          &v38,
          (__int64)&v32);
      }
      v25 = lpMem;
      v26 = lpMem == 0;
      lpMem = 0;
      if ( !v26 )
      {
        v27 = GetProcessHeap();
        HeapFree(v27, 0, v25);
      }
      v12 = (unsigned int)(v12 + 1);
      v5 = (LPVOID *)v41;
      if ( (unsigned int)v12 >= *((_DWORD *)this + 154) )
        goto LABEL_18;
    }
  }
  *a4 = v7;
  v8 = -2147024809;
  v9 = 337;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\extension\\extensionkey.cpp",
    (const char *)(unsigned int)v8,
    pdwType);
  return v8;
}

```

## disassembly

```asm
0x180014d68  push    rbp
0x180014d6a  push    rbx
0x180014d6b  push    rsi
0x180014d6c  push    rdi
0x180014d6d  push    r12
0x180014d6f  push    r13
0x180014d71  push    r14
0x180014d73  push    r15
0x180014d75  lea     rbp, [rsp-1C8h]
0x180014d7d  sub     rsp, 2C8h
0x180014d84  mov     rax, cs:__security_cookie
0x180014d8b  xor     rax, rsp
0x180014d8e  mov     [rbp+200h+var_50], rax
0x180014d95  mov     r15, r9
0x180014d98  mov     [rbp+200h+var_278], r8
0x180014d9c  mov     rdi, rdx
0x180014d9f  mov     [rbp+200h+var_270], rdx
0x180014da3  mov     rsi, rcx
0x180014da6  mov     eax, [rcx+268h]
0x180014dac  cmp     [r9], eax
0x180014daf  jnb     short loc_180014DDB
0x180014db1  mov     [r9], eax
0x180014db4  mov     ebx, 80070057h
0x180014db9  mov     edx, 151h; void *
0x180014dbe  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014dc5  mov     r9d, ebx; char *
0x180014dc8  mov     rcx, [rbp+208h]; this
0x180014dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014dd4  mov     eax, ebx
0x180014dd6  jmp     loc_180014FB1
0x180014ddb  xor     r12d, r12d
0x180014dde  xor     r14d, r14d
0x180014de1  test    eax, eax
0x180014de3  jz      loc_180014FAC
0x180014de9  mov     [rsp+300h+lpValue], 0
0x180014df2  mov     rax, [rsi+260h]
0x180014df9  mov     rcx, [rax+r14*8]
0x180014dfd  mov     rax, [rcx]
0x180014e00  lea     rdx, [rsp+300h+lpValue]
0x180014e05  mov     rax, [rax+28h]
0x180014e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0e  mov     ebx, eax
0x180014e10  test    eax, eax
0x180014e12  js      loc_18001503A
0x180014e18  mov     [rsp+300h+var_2A8], 20Ah
0x180014e20  lea     rax, [rsp+300h+var_2A8]
0x180014e25  mov     [rsp+300h+pcbData], rax; pcbData
0x180014e2a  lea     rax, [rbp+200h+psz]
0x180014e2e  mov     [rsp+300h+pvData], rax; pvData
0x180014e33  xor     ebx, ebx
0x180014e35  mov     [rsp+300h+pdwType], rbx; unsigned int
0x180014e3a  lea     r9d, [rbx+2]; dwFlags
0x180014e3e  mov     r8, [rsp+300h+lpValue]; lpValue
0x180014e43  xor     edx, edx; lpSubKey
0x180014e45  mov     rcx, [rsi+270h]; hkey
0x180014e4c  call    cs:__imp_RegGetValueW
0x180014e52  test    eax, eax
0x180014e54  jnz     loc_18001501A
0x180014e5a  mov     [rsp+300h+lpMem], rbx
0x180014e5f  lea     rax, [rsp+300h+lpMem]
0x180014e64  mov     [rsp+300h+var_2A0], rax
0x180014e69  mov     [rsp+300h+var_298], rbx
0x180014e6e  mov     [rsp+300h+var_290], 1
0x180014e73  lea     r9, [rsp+300h+var_2B8]; unsigned int *
0x180014e78  lea     r8, [rsp+300h+var_298]; unsigned __int16 **
0x180014e7d  lea     rdx, [rbp+200h+psz]; psz
0x180014e81  mov     rcx, rdi; ppv
0x180014e84  call    ?QueryNodeValue@CfgMgrHelper@@QEAAJPEBGPEAPEAGPEAK@Z; CfgMgrHelper::QueryNodeValue(ushort const *,ushort * *,ulong *)
0x180014e89  mov     edi, eax
0x180014e8b  cmp     [rsp+300h+var_290], bl
0x180014e8f  jz      short loc_180014EBA
0x180014e91  mov     rdx, [rsp+300h+var_2A0]
0x180014e96  mov     rbx, [rdx]
0x180014e99  mov     rcx, [rsp+300h+var_298]
0x180014e9e  mov     [rdx], rcx
0x180014ea1  test    rbx, rbx
0x180014ea4  jz      short loc_180014EBA
0x180014ea6  call    cs:__imp_GetProcessHeap
0x180014eac  mov     rcx, rax; hHeap
0x180014eaf  mov     r8, rbx; lpMem
0x180014eb2  xor     edx, edx; dwFlags
0x180014eb4  call    cs:__imp_HeapFree
0x180014eba  test    edi, edi
0x180014ebc  jns     short loc_180014F11
0x180014ebe  mov     eax, cs:dword_180052170
0x180014ec4  cmp     eax, 2
0x180014ec7  jbe     loc_180014F71
0x180014ecd  mov     [rsp+300h+var_2B8], edi
0x180014ed1  mov     rax, [rsp+300h+lpValue]
0x180014ed6  mov     [rsp+300h+var_288], rax
0x180014edb  lea     rax, aExtensionHandl; "Extension handler"
0x180014ee2  mov     [rbp+200h+var_280], rax
0x180014ee6  lea     rax, [rsp+300h+var_2B8]
0x180014eeb  mov     [rsp+300h+pcbData], rax
0x180014ef0  lea     rax, [rsp+300h+var_288]
0x180014ef5  mov     [rsp+300h+pvData], rax
0x180014efa  lea     rax, [rbp+200h+var_280]
0x180014efe  mov     [rsp+300h+pdwType], rax
0x180014f03  lea     rdx, byte_18004960D
0x180014f0a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014f0f  jmp     short loc_180014F71
0x180014f11  mov     rax, [rsi+260h]
0x180014f18  mov     rcx, [rax+r14*8]
0x180014f1c  mov     rax, [rcx]
0x180014f1f  mov     rdx, [rsp+300h+lpMem]
0x180014f24  mov     rax, [rax+20h]
0x180014f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f2d  mov     edi, eax
0x180014f2f  test    eax, eax
0x180014f31  js      loc_180014FD4
0x180014f37  mov     r9, [rsp+300h+lpMem]; unsigned __int16 *
0x180014f3c  mov     r8, [rsp+300h+lpValue]; unsigned __int16 *
0x180014f41  xor     edx, edx; unsigned __int16 *
0x180014f43  lea     rcx, aExtensionHandl; "Extension handler"
0x180014f4a  call    ?LogHandlerKeysReturned@@YAXPEBG000@Z; LogHandlerKeysReturned(ushort const *,ushort const *,ushort const *,ushort const *)
0x180014f4f  mov     rax, [rsi+260h]
0x180014f56  mov     rcx, [rax+r14*8]
0x180014f5a  mov     rdx, [rbp+200h+var_278]
0x180014f5e  mov     [rdx+r12*8], rcx
0x180014f62  mov     rax, [rcx]
0x180014f65  mov     rax, [rax+8]
0x180014f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6e  inc     r12d
0x180014f71  mov     rbx, [rsp+300h+lpMem]
0x180014f76  test    rbx, rbx
0x180014f79  mov     [rsp+300h+lpMem], 0
0x180014f82  jz      short loc_180014F98
0x180014f84  call    cs:__imp_GetProcessHeap
0x180014f8a  mov     r8, rbx; lpMem
0x180014f8d  xor     edx, edx; dwFlags
0x180014f8f  mov     rcx, rax; hHeap
0x180014f92  call    cs:__imp_HeapFree
0x180014f98  inc     r14d
0x180014f9b  cmp     r14d, [rsi+268h]
0x180014fa2  mov     rdi, [rbp+200h+var_270]
0x180014fa6  jb      loc_180014DE9
0x180014fac  mov     [r15], r12d
0x180014faf  xor     eax, eax
0x180014fb1  mov     rcx, [rbp+200h+var_50]
0x180014fb8  xor     rcx, rsp; StackCookie
0x180014fbb  call    __security_check_cookie
0x180014fc0  add     rsp, 2C8h
0x180014fc7  pop     r15
0x180014fc9  pop     r14
0x180014fcb  pop     r13
0x180014fcd  pop     r12
0x180014fcf  pop     rdi
0x180014fd0  pop     rsi
0x180014fd1  pop     rbx
0x180014fd2  pop     rbp
0x180014fd3  retn
0x180014fd4  mov     rcx, [rbp+208h]; this
0x180014fdb  mov     r9d, edi; char *
0x180014fde  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014fe5  mov     edx, 173h; void *
0x180014fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fef  mov     rbx, [rsp+300h+lpMem]
0x180014ff4  mov     [rsp+300h+lpMem], 0
0x180014ffd  test    rbx, rbx
0x180015000  jz      short loc_180015016
0x180015002  call    cs:__imp_GetProcessHeap
0x180015008  mov     rcx, rax; hHeap
0x18001500b  mov     r8, rbx; lpMem
0x18001500e  xor     edx, edx; dwFlags
0x180015010  call    cs:__imp_HeapFree
0x180015016  mov     eax, edi
0x180015018  jmp     short loc_180014FB1
0x18001501a  mov     rcx, [rbp+208h]; this
0x180015021  mov     r9d, eax; char *
0x180015024  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001502b  mov     edx, 15Fh; void *
0x180015030  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015035  jmp     loc_180014FB1
0x18001503a  mov     edx, 15Ah
0x18001503f  jmp     loc_180014DBE
```
