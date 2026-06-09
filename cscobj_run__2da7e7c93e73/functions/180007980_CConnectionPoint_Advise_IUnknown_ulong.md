# CConnectionPoint::Advise(IUnknown *,ulong *)

- ea: `0x180007980`
- end: `0x180007c80`
- name: `?Advise@CConnectionPoint@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `768`
- prototype: `__int64 __fastcall(CConnectionPoint *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002d80`
- `0x180007980`
- `0x180008810`
- `0x180010d90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007b6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007bd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007bd1`

## pseudocode

```c
__int64 __fastcall CConnectionPoint::Advise(CConnectionPoint *this, struct IUnknown *a2, unsigned int *a3)
{
  int Instance; // ebx
  unsigned int v7; // ecx
  char *v8; // rbp
  _QWORD *v9; // rdx
  __int64 v10; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  int v12; // ecx
  __int64 v13; // rdx
  void **v14; // r9
  unsigned __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r12
  _QWORD *v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // edi
  __int64 (__fastcall *v22)(__int64, struct IUnknown *, char *, _QWORD, SIZE_T *); // rbx
  DWORD CurrentProcessId; // eax
  unsigned int v24; // eax
  _QWORD v26[4]; // [rsp+30h] [rbp-58h]
  SIZE_T dwBytes; // [rsp+98h] [rbp+10h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  Instance = -2147220990;
  v26[0] = &IID_IOfflineFilesEvents;
  v26[1] = &IID_IOfflineFilesEvents2;
  v7 = 0;
  v26[2] = &IID_IOfflineFilesEvents3;
  v26[3] = &IID_IOfflineFilesEvents4;
  while ( v7 < 4 )
  {
    v8 = (char *)this + 12;
    v9 = (_QWORD *)v26[v7];
    v10 = *v9 - *(_QWORD *)((char *)this + 12);
    if ( *v9 == *(_QWORD *)((char *)this + 12) )
      v10 = v9[1] - *(_QWORD *)((char *)this + 20);
    if ( !v10 )
    {
      lpVtbl = a2->lpVtbl;
      dwBytes = 0;
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, char *, SIZE_T *))lpVtbl->QueryInterface)(
              a2,
              (char *)this + 12,
              &dwBytes);
      if ( v12 < 0 )
      {
        if ( v12 == -2147467262 )
          return (unsigned int)-2147220990;
        return (unsigned int)v12;
      }
      else
      {
        (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
        if ( !*((_QWORD *)this + 4) )
        {
          *((_QWORD *)this + 4) = 0;
          dwBytes = 0;
          Instance = ULongLongMult(0xAu, 0x10u, &dwBytes);
          if ( Instance >= 0 )
            Instance = UstVarLib::CscUtil_HeapAlloc(dwBytes, v13, (_QWORD *)this + 4, v14);
          if ( Instance < 0 )
            return (unsigned int)Instance;
          *((_QWORD *)this + 5) = 10;
        }
        v15 = *((_QWORD *)this + 5);
        v16 = 0;
        v17 = *((_QWORD *)this + 4);
        while ( v16 < v15 )
        {
          v18 = v17 + 16LL * v16;
          if ( !*(_QWORD *)v18 )
            goto LABEL_21;
          ++v16;
        }
        Instance = CscUtil_HeapReAllocArray<tagCONNECTDATA>(v17, v15 + 10, (char *)this + 32);
        if ( Instance < 0 )
          return (unsigned int)Instance;
        v18 = *((_QWORD *)this + 4) + 16LL * *((_QWORD *)this + 5);
        *((_QWORD *)this + 5) += 10LL;
LABEL_21:
        v19 = (_QWORD *)*((_QWORD *)this + 7);
        Instance = -2147467262;
        v28 = 0;
        v20 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v19;
        if ( *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 == *v19 )
          v20 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v19[1];
        if ( !v20 )
        {
          v21 = *((_DWORD *)this + 16);
          if ( v21 )
          {
            dwBytes = 0;
            Instance = CoCreateInstance(
                         &CLSID_StdGlobalInterfaceTable,
                         0,
                         1u,
                         &GUID_00000146_0000_0000_c000_000000000046,
                         (LPVOID *)&dwBytes);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(SIZE_T, _QWORD, GUID *, __int64 *))(*(_QWORD *)dwBytes + 40LL))(
                           dwBytes,
                           v21,
                           &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
                           &v28);
              (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)dwBytes + 16LL))(dwBytes);
            }
            if ( Instance >= 0 )
            {
              LODWORD(dwBytes) = 0;
              v22 = *(__int64 (__fastcall **)(__int64, struct IUnknown *, char *, _QWORD, SIZE_T *))(*(_QWORD *)v28 + 32LL);
              CurrentProcessId = GetCurrentProcessId();
              Instance = v22(v28, a2, v8, CurrentProcessId, &dwBytes);
              if ( Instance >= 0 )
              {
                ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
                v24 = dwBytes;
                *(_DWORD *)(v18 + 8) = dwBytes;
                *(_QWORD *)v18 = a2;
                *a3 = v24;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
          }
        }
      }
      return (unsigned int)Instance;
    }
    ++v7;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007980  mov     r11, rsp
0x180007983  push    rdi
0x180007984  push    r14
0x180007986  push    r15
0x180007988  sub     rsp, 70h
0x18000798c  mov     r15, r8
0x18000798f  mov     r14, rdx
0x180007992  mov     rdi, rcx
0x180007995  test    rdx, rdx
0x180007998  jz      loc_180007C71
0x18000799e  test    r8, r8
0x1800079a1  jz      loc_180007C71
0x1800079a7  mov     [r11+8], rbx
0x1800079ab  lea     rax, IID_IOfflineFilesEvents
0x1800079b2  mov     [r11-38h], r13
0x1800079b6  mov     ebx, 80040202h
0x1800079bb  mov     [r11-58h], rax
0x1800079bf  xor     r13d, r13d
0x1800079c2  lea     rax, IID_IOfflineFilesEvents2
0x1800079c9  mov     [r11-20h], rbp
0x1800079cd  mov     [r11-50h], rax
0x1800079d1  mov     ecx, r13d
0x1800079d4  lea     rax, IID_IOfflineFilesEvents3
0x1800079db  mov     [r11-28h], rsi
0x1800079df  mov     [r11-48h], rax
0x1800079e3  lea     rax, IID_IOfflineFilesEvents4
0x1800079ea  mov     [r11-40h], rax
0x1800079ee  mov     [r11-30h], r12
0x1800079f2  cmp     ecx, 4
0x1800079f5  jnb     loc_180007C49
0x1800079fb  movsxd  rax, ecx
0x1800079fe  lea     rbp, [rdi+0Ch]
0x180007a02  mov     rdx, [rsp+rax*8+88h+var_58]
0x180007a07  mov     rax, [rdx]
0x180007a0a  sub     rax, [rbp+0]
0x180007a0e  jnz     short loc_180007A18
0x180007a10  mov     rax, [rdx+8]
0x180007a14  sub     rax, [rbp+8]
0x180007a18  test    rax, rax
0x180007a1b  jz      short loc_180007A21
0x180007a1d  inc     ecx
0x180007a1f  jmp     short loc_1800079F2
0x180007a21  mov     rax, [r14]
0x180007a24  lea     r8, [rsp+88h+dwBytes]
0x180007a2c  mov     rdx, rbp
0x180007a2f  mov     [rsp+88h+dwBytes], r13
0x180007a37  mov     rcx, r14
0x180007a3a  mov     rax, [rax]
0x180007a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a42  mov     ecx, eax
0x180007a44  test    eax, eax
0x180007a46  js      loc_180007C3B
0x180007a4c  mov     rcx, [rsp+88h+dwBytes]
0x180007a54  mov     rax, [rcx]
0x180007a57  mov     rax, [rax+10h]
0x180007a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a60  cmp     [rdi+20h], r13
0x180007a64  jnz     short loc_180007AB2
0x180007a66  lea     r8, [rsp+88h+dwBytes]; unsigned __int64 *
0x180007a6e  mov     [rdi+20h], r13
0x180007a72  mov     edx, 10h; unsigned __int64
0x180007a77  mov     [rsp+88h+dwBytes], r13
0x180007a7f  mov     ecx, 0Ah; unsigned __int64
0x180007a84  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180007a89  mov     ebx, eax
0x180007a8b  test    eax, eax
0x180007a8d  js      short loc_180007AA2
0x180007a8f  mov     rcx, [rsp+88h+dwBytes]; dwBytes
0x180007a97  lea     r8, [rdi+20h]; int
0x180007a9b  call    ?CscUtil_HeapAlloc@UstVarLib@@YAJ_KHPEAPEAXPEAX@Z; UstVarLib::CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180007aa0  mov     ebx, eax
0x180007aa2  test    ebx, ebx
0x180007aa4  js      loc_180007C49
0x180007aaa  mov     qword ptr [rdi+28h], 0Ah
0x180007ab2  mov     rdx, [rdi+28h]
0x180007ab6  mov     eax, r13d
0x180007ab9  mov     rcx, [rdi+20h]
0x180007abd  movsxd  r8, eax
0x180007ac0  cmp     r8, rdx
0x180007ac3  jnb     short loc_180007AD6
0x180007ac5  add     r8, r8
0x180007ac8  cmp     [rcx+r8*8], r13
0x180007acc  lea     r12, [rcx+r8*8]
0x180007ad0  jz      short loc_180007B04
0x180007ad2  inc     eax
0x180007ad4  jmp     short loc_180007ABD
0x180007ad6  add     rdx, 0Ah
0x180007ada  lea     r8, [rdi+20h]
0x180007ade  call    ??$CscUtil_HeapReAllocArray@UtagCONNECTDATA@@@@YAJPEAUtagCONNECTDATA@@_KPEAPEAU0@@Z; CscUtil_HeapReAllocArray<tagCONNECTDATA>(tagCONNECTDATA *,unsigned __int64,tagCONNECTDATA * *)
0x180007ae3  mov     ebx, eax
0x180007ae5  test    eax, eax
0x180007ae7  js      loc_180007C49
0x180007aed  mov     rax, [rdi+28h]
0x180007af1  mov     r12, rax
0x180007af4  shl     r12, 4
0x180007af8  add     r12, [rdi+20h]
0x180007afc  add     rax, 0Ah
0x180007b00  mov     [rdi+28h], rax
0x180007b04  mov     rcx, [rdi+38h]
0x180007b08  mov     ebx, 80004002h
0x180007b0d  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x180007b14  mov     [rsp+88h+arg_18], r13
0x180007b1c  sub     rax, [rcx]
0x180007b1f  jnz     short loc_180007B2C
0x180007b21  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x180007b28  sub     rax, [rcx+8]
0x180007b2c  test    rax, rax
0x180007b2f  jnz     loc_180007C49
0x180007b35  mov     edi, [rdi+40h]
0x180007b38  test    edi, edi
0x180007b3a  jz      loc_180007C49
0x180007b40  lea     rax, [rsp+88h+dwBytes]
0x180007b48  mov     [rsp+88h+dwBytes], r13
0x180007b50  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007b57  mov     [rsp+88h+ppv], rax; ppv
0x180007b5c  xor     edx, edx; pUnkOuter
0x180007b5e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007b65  mov     r8d, 1; dwClsContext
0x180007b6b  call    cs:__imp_CoCreateInstance
0x180007b71  mov     ebx, eax
0x180007b73  test    eax, eax
0x180007b75  js      short loc_180007BB2
0x180007b77  mov     rcx, [rsp+88h+dwBytes]
0x180007b7f  lea     r9, [rsp+88h+arg_18]
0x180007b87  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180007b8e  mov     edx, edi
0x180007b90  mov     rax, [rcx]
0x180007b93  mov     rax, [rax+28h]
0x180007b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9c  mov     rcx, [rsp+88h+dwBytes]
0x180007ba4  mov     ebx, eax
0x180007ba6  mov     rax, [rcx]
0x180007ba9  mov     rax, [rax+10h]
0x180007bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb2  test    ebx, ebx
0x180007bb4  js      loc_180007C49
0x180007bba  mov     rax, [rsp+88h+arg_18]
0x180007bc2  mov     dword ptr [rsp+88h+dwBytes], r13d
0x180007bca  mov     rcx, [rax]
0x180007bcd  mov     rbx, [rcx+20h]
0x180007bd1  call    cs:__imp_GetCurrentProcessId
0x180007bd7  lea     rcx, [rsp+88h+dwBytes]
0x180007bdf  mov     r8, rbp
0x180007be2  mov     [rsp+88h+ppv], rcx
0x180007be7  mov     r9d, eax
0x180007bea  mov     rcx, [rsp+88h+arg_18]
0x180007bf2  mov     rdx, r14
0x180007bf5  mov     rax, rbx
0x180007bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bfd  mov     ebx, eax
0x180007bff  test    eax, eax
0x180007c01  js      short loc_180007C25
0x180007c03  mov     rax, [r14]
0x180007c06  mov     rcx, r14
0x180007c09  mov     rax, [rax+8]
0x180007c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c12  mov     eax, dword ptr [rsp+88h+dwBytes]
0x180007c19  mov     [r12+8], eax
0x180007c1e  mov     [r12], r14
0x180007c22  mov     [r15], eax
0x180007c25  mov     rcx, [rsp+88h+arg_18]
0x180007c2d  mov     rax, [rcx]
0x180007c30  mov     rax, [rax+10h]
0x180007c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c39  jmp     short loc_180007C49
0x180007c3b  mov     eax, ebx
0x180007c3d  mov     ebx, 80004002h
0x180007c42  cmp     ecx, ebx
0x180007c44  cmovz   ecx, eax
0x180007c47  mov     ebx, ecx
0x180007c49  mov     r13, [rsp+88h+var_38]
0x180007c4e  mov     eax, ebx
0x180007c50  mov     rbx, [rsp+88h+arg_0]
0x180007c58  mov     r12, [rsp+88h+var_30]
0x180007c5d  mov     rsi, [rsp+88h+var_28]
0x180007c62  mov     rbp, [rsp+88h+var_20]
0x180007c67  add     rsp, 70h
0x180007c6b  pop     r15
0x180007c6d  pop     r14
0x180007c6f  pop     rdi
0x180007c70  retn
0x180007c71  mov     eax, 80004003h
0x180007c76  add     rsp, 70h
0x180007c7a  pop     r15
0x180007c7c  pop     r14
0x180007c7e  pop     rdi
0x180007c7f  retn
```
