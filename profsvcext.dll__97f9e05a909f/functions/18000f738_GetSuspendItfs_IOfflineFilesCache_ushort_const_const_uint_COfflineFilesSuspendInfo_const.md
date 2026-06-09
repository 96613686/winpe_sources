# GetSuspendItfs(IOfflineFilesCache *,ushort const * * const,uint,COfflineFilesSuspendInfo * const)

- ea: `0x18000f738`
- end: `0x18000f865`
- name: `?GetSuspendItfs@@YAXPEAUIOfflineFilesCache@@QEAPEBGIQEAVCOfflineFilesSuspendInfo@@@Z`
- size: `301`
- prototype: `void __fastcall(struct IOfflineFilesCache *, const unsigned __int16 **const, unsigned int, struct COfflineFilesSuspendInfo *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005b54`

## callees

- `0x180005acc`
- `0x18000f738`
- `0x180020010`

## pseudocode

```c
void __fastcall GetSuspendItfs(
        struct IOfflineFilesCache *a1,
        const unsigned __int16 **const a2,
        unsigned int a3,
        struct COfflineFilesSuspendInfo *const a4)
{
  unsigned int v4; // r14d
  __int64 v6; // rsi
  const unsigned __int16 **v8; // r15
  struct IOfflineFilesCache *v9; // rdi
  struct IOfflineFilesCacheVtbl *lpVtbl; // rax
  HRESULT (__stdcall *FindItem)(IOfflineFilesCache *, LPCWSTR, DWORD, IOfflineFilesItem **); // rbx
  int v12; // r15d
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  char *v15; // rdi
  __int64 v16; // rbx
  char *v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF

  if ( a3 )
  {
    v4 = 0;
    v6 = 0;
    v8 = a2;
    v9 = a1;
    while ( 1 )
    {
      lpVtbl = v9->lpVtbl;
      v19 = 0;
      v18 = 0;
      FindItem = lpVtbl->FindItem;
      Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v19);
      v12 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, const unsigned __int16 *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))FindItem)(
              v9,
              v8[v6],
              0,
              &v19);
      if ( v12 >= 0 )
      {
        v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
        v14 = **v19;
        Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v18);
        v12 = v14(v13, &GUID_62c4560f_bc0b_48ca_ad9d_34cb528d99a9, &v18);
      }
      v15 = (char *)a4 + 16 * v6;
      if ( v12 < 0 )
        break;
      v16 = v18;
      if ( *(_QWORD *)v15 != v18 )
      {
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
        v17 = (char *)&v20;
        v20 = *(_QWORD *)v15;
        *(_QWORD *)v15 = v16;
        goto LABEL_11;
      }
LABEL_12:
      *((_DWORD *)v15 + 2) = v12;
      Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v18);
      Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v19);
      v9 = a1;
      ++v4;
      v8 = a2;
      ++v6;
      if ( v4 >= a3 )
        return;
    }
    v17 = (char *)a4 + 16 * v6;
LABEL_11:
    Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(v17);
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x18000f738  test    r8d, r8d
0x18000f73b  jz      locret_18000F864
0x18000f741  mov     [rsp-38h+arg_10], rbx
0x18000f746  mov     [rsp-38h+arg_8], rdx
0x18000f74b  mov     [rsp-38h+arg_0], rcx
0x18000f750  push    rbp
0x18000f751  push    rsi
0x18000f752  push    rdi
0x18000f753  push    r12
0x18000f755  push    r13
0x18000f757  push    r14
0x18000f759  push    r15
0x18000f75b  mov     rbp, rsp
0x18000f75e  sub     rsp, 50h
0x18000f762  xor     r14d, r14d
0x18000f765  mov     r13, r9
0x18000f768  xor     esi, esi
0x18000f76a  mov     r12d, r8d
0x18000f76d  mov     r15, rdx
0x18000f770  mov     rdi, rcx
0x18000f773  mov     rax, [rdi]
0x18000f776  lea     rcx, [rbp+var_18]
0x18000f77a  mov     [rbp+var_18], 0
0x18000f782  mov     [rbp+var_20], 0
0x18000f78a  mov     rbx, [rax+50h]
0x18000f78e  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x18000f793  mov     rdx, [r15+rsi*8]
0x18000f797  lea     r9, [rbp+var_18]
0x18000f79b  xor     r8d, r8d
0x18000f79e  mov     rcx, rdi
0x18000f7a1  mov     rax, rbx
0x18000f7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7a9  mov     r15d, eax
0x18000f7ac  test    eax, eax
0x18000f7ae  js      short loc_18000F7DC
0x18000f7b0  mov     rbx, [rbp+var_18]
0x18000f7b4  lea     rcx, [rbp+var_20]
0x18000f7b8  mov     rax, [rbx]
0x18000f7bb  mov     rdi, [rax]
0x18000f7be  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x18000f7c3  lea     r8, [rbp+var_20]
0x18000f7c7  mov     rcx, rbx
0x18000f7ca  lea     rdx, _GUID_62c4560f_bc0b_48ca_ad9d_34cb528d99a9
0x18000f7d1  mov     rax, rdi
0x18000f7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7d9  mov     r15d, eax
0x18000f7dc  mov     rdi, rsi
0x18000f7df  shl     rdi, 4
0x18000f7e3  add     rdi, r13
0x18000f7e6  test    r15d, r15d
0x18000f7e9  js      short loc_18000F818
0x18000f7eb  mov     rbx, [rbp+var_20]
0x18000f7ef  cmp     [rdi], rbx
0x18000f7f2  jz      short loc_18000F820
0x18000f7f4  test    rbx, rbx
0x18000f7f7  jz      short loc_18000F808
0x18000f7f9  mov     rax, [rbx]
0x18000f7fc  mov     rcx, rbx
0x18000f7ff  mov     rax, [rax+8]
0x18000f803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f808  mov     rax, [rdi]
0x18000f80b  lea     rcx, [rbp+var_10]
0x18000f80f  mov     [rbp+var_10], rax
0x18000f813  mov     [rdi], rbx
0x18000f816  jmp     short loc_18000F81B
0x18000f818  mov     rcx, rdi
0x18000f81b  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x18000f820  lea     rcx, [rbp+var_20]
0x18000f824  mov     [rdi+8], r15d
0x18000f828  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x18000f82d  lea     rcx, [rbp+var_18]
0x18000f831  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x18000f836  mov     rdi, [rbp+arg_0]
0x18000f83a  inc     r14d
0x18000f83d  mov     r15, [rbp+arg_8]
0x18000f841  inc     rsi
0x18000f844  cmp     r14d, r12d
0x18000f847  jb      loc_18000F773
0x18000f84d  mov     rbx, [rsp+50h+arg_10]
0x18000f855  add     rsp, 50h
0x18000f859  pop     r15
0x18000f85b  pop     r14
0x18000f85d  pop     r13
0x18000f85f  pop     r12
0x18000f861  pop     rdi
0x18000f862  pop     rsi
0x18000f863  pop     rbp
0x18000f864  retn
```
