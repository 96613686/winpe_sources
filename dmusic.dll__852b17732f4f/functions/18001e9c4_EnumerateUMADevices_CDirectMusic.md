# EnumerateUMADevices(CDirectMusic *)

- ea: `0x18001e9c4`
- end: `0x18001ec00`
- name: `?EnumerateUMADevices@@YAJPEAVCDirectMusic@@@Z`
- size: `572`
- prototype: `__int64 __fastcall(struct CDirectMusic *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013ed4`

## callees

- `0x1800012c4`
- `0x18001e2b0`
- `0x18001e9c4`
- `0x180020ff8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ea87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ea87`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyA` at `0x18001ea5c`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyA` at `0x18001ea5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb81`
- `api-ms-win-mm-mme-l1-1-0!waveOutMessage` at `0x18001ea16`
- `api-ms-win-mm-mme-l1-1-0!waveOutMessage` at `0x18001ea16`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EnumerateUMADevices(struct CDirectMusic *a1)
{
  unsigned __int64 v2; // rdx
  char *v3; // rdi
  unsigned __int64 v4; // rdx
  HRESULT v5; // esi
  LPVOID v6; // rcx
  unsigned int i; // ebx
  unsigned int v9; // [rsp+30h] [rbp-40h] BYREF
  LPVOID v10; // [rsp+38h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+48h] [rbp-28h] BYREF
  void *v13; // [rsp+50h] [rbp-20h] BYREF
  struct IMMDevice *v14; // [rsp+58h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+A8h] [rbp+38h] BYREF
  DWORD_PTR dw1; // [rsp+B0h] [rbp+40h] BYREF
  DWORD_PTR dw2; // [rsp+B8h] [rbp+48h] BYREF

  phkResult = 0;
  v9 = 0;
  v16 = 0;
  ppv = 0;
  v10 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  LODWORD(dw1) = 0;
  LODWORD(dw2) = 0;
  if ( waveOutMessage((HWAVEOUT)0xFFFFFFFFFFFFFFFFLL, 0x2015u, (DWORD_PTR)&dw1, (DWORD_PTR)&dw2) || (_DWORD)dw1 == -1 )
  {
LABEL_6:
    v3 = 0;
    goto LABEL_7;
  }
  if ( !(unsigned int)WaveOutIdToInstanceId((unsigned int)dw1, &v13) )
  {
    if ( v13 )
      operator delete(v13, v2);
    goto LABEL_6;
  }
  v3 = (char *)v13;
LABEL_7:
  if ( RegCreateKeyA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Control\\MediaProperties\\PrivateProperties\\Midi\\UMAPort",
         &phkResult) )
  {
    phkResult = 0;
  }
  v5 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &ppv);
  if ( v5 >= 0 )
  {
    v6 = v10;
    if ( v10 != ppv )
    {
      v6 = 0;
      v10 = 0;
      if ( ppv )
      {
        (**(void (__fastcall ***)(LPVOID, GUID *, void **))ppv)(ppv, &GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0, &v10);
        v6 = v10;
      }
    }
    v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)v6 + 32LL))(
           v6,
           &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196,
           &v12);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 24LL))(v12, &v16);
      if ( v5 >= 0 )
      {
        for ( i = 0; i < v16; ++i )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v12 + 32LL))(v12, i, &v14);
          if ( v5 >= 0 )
            EnumerateUMADevice(a1, phkResult, v3, v14, i, &v9);
        }
      }
    }
  }
  if ( v3 )
    operator delete(v3, v4);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v14 )
    ((void (__fastcall *)(struct IMMDevice *))v14->lpVtbl->Release)(v14);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v10 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e9c4  mov     [rsp-28h+arg_0], rbx
0x18001e9c9  push    rbp
0x18001e9ca  push    rsi
0x18001e9cb  push    rdi
0x18001e9cc  push    r14
0x18001e9ce  push    r15
0x18001e9d0  mov     rbp, rsp
0x18001e9d3  sub     rsp, 70h
0x18001e9d7  mov     r14, rcx
0x18001e9da  xor     r15d, r15d
0x18001e9dd  mov     [rbp+phkResult], r15
0x18001e9e1  mov     [rbp+var_40], r15d
0x18001e9e5  mov     [rbp+arg_8], r15d
0x18001e9e9  mov     [rbp+var_10], r15
0x18001e9ed  mov     [rbp+var_38], r15
0x18001e9f1  mov     [rbp+var_28], r15
0x18001e9f5  mov     [rbp+var_18], r15
0x18001e9f9  mov     [rbp+var_20], r15
0x18001e9fd  mov     dword ptr [rbp+dw1], r15d
0x18001ea01  mov     dword ptr [rbp+dw2], r15d
0x18001ea05  lea     r9, [rbp+dw2]; dw2
0x18001ea09  lea     r8, [rbp+dw1]; dw1
0x18001ea0d  mov     edx, 2015h; uMsg
0x18001ea12  or      rcx, 0FFFFFFFFFFFFFFFFh; hwo
0x18001ea16  call    cs:__imp_waveOutMessage
0x18001ea1c  test    eax, eax
0x18001ea1e  jnz     short loc_18001EA47
0x18001ea20  mov     ecx, dword ptr [rbp+dw1]
0x18001ea23  cmp     ecx, 0FFFFFFFFh
0x18001ea26  jz      short loc_18001EA47
0x18001ea28  lea     rdx, [rbp+var_20]
0x18001ea2c  call    WaveOutIdToInstanceId
0x18001ea31  test    eax, eax
0x18001ea33  jnz     loc_18001EBF6
0x18001ea39  mov     rcx, [rbp+var_20]; void *
0x18001ea3d  test    rcx, rcx
0x18001ea40  jz      short loc_18001EA47
0x18001ea42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ea47  mov     rdi, r15
0x18001ea4a  lea     r8, [rbp+phkResult]; phkResult
0x18001ea4e  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Med"...
0x18001ea55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ea5c  call    cs:__imp_RegCreateKeyA
0x18001ea62  test    eax, eax
0x18001ea64  jz      short loc_18001EA6A
0x18001ea66  mov     [rbp+phkResult], r15
0x18001ea6a  lea     rax, [rbp+var_10]
0x18001ea6e  mov     [rsp+70h+ppv], rax; ppv
0x18001ea73  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18001ea7a  xor     edx, edx; pUnkOuter
0x18001ea7c  lea     r8d, [rdx+17h]; dwClsContext
0x18001ea80  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x18001ea87  call    cs:__imp_CoCreateInstance
0x18001ea8d  mov     esi, eax
0x18001ea8f  test    eax, eax
0x18001ea91  js      loc_18001EB6B
0x18001ea97  mov     r9, [rbp+var_10]
0x18001ea9b  mov     rcx, [rbp+var_38]
0x18001ea9f  cmp     rcx, r9
0x18001eaa2  jz      short loc_18001EAE8
0x18001eaa4  mov     rbx, rcx
0x18001eaa7  mov     rcx, r15
0x18001eaaa  mov     [rbp+var_38], rcx
0x18001eaae  test    r9, r9
0x18001eab1  jz      short loc_18001EAD0
0x18001eab3  mov     rax, [r9]
0x18001eab6  lea     r8, [rbp+var_38]
0x18001eaba  lea     rdx, _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0
0x18001eac1  mov     rcx, r9
0x18001eac4  mov     rax, [rax]
0x18001eac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eacc  mov     rcx, [rbp+var_38]
0x18001ead0  test    rbx, rbx
0x18001ead3  jz      short loc_18001EAE8
0x18001ead5  mov     rax, [rbx]
0x18001ead8  mov     rcx, rbx
0x18001eadb  mov     rax, [rax+10h]
0x18001eadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eae4  mov     rcx, [rbp+var_38]
0x18001eae8  mov     rax, [rcx]
0x18001eaeb  lea     r8, [rbp+var_28]
0x18001eaef  lea     rdx, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x18001eaf6  mov     rax, [rax+20h]
0x18001eafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaff  mov     esi, eax
0x18001eb01  test    eax, eax
0x18001eb03  js      short loc_18001EB6B
0x18001eb05  mov     rcx, [rbp+var_28]
0x18001eb09  mov     rax, [rcx]
0x18001eb0c  lea     rdx, [rbp+arg_8]
0x18001eb10  mov     rax, [rax+18h]
0x18001eb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb19  mov     esi, eax
0x18001eb1b  test    eax, eax
0x18001eb1d  js      short loc_18001EB6B
0x18001eb1f  mov     ebx, r15d
0x18001eb22  cmp     [rbp+arg_8], r15d
0x18001eb26  jbe     short loc_18001EB6B
0x18001eb28  mov     rcx, [rbp+var_28]
0x18001eb2c  mov     rax, [rcx]
0x18001eb2f  lea     r8, [rbp+var_18]
0x18001eb33  mov     edx, ebx
0x18001eb35  mov     rax, [rax+20h]
0x18001eb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb3e  mov     esi, eax
0x18001eb40  test    eax, eax
0x18001eb42  js      short loc_18001EB64
0x18001eb44  lea     rax, [rbp+var_40]
0x18001eb48  mov     [rsp+70h+var_48], rax; unsigned int *
0x18001eb4d  mov     dword ptr [rsp+70h+ppv], ebx; unsigned int
0x18001eb51  mov     r9, [rbp+var_18]; struct IMMDevice *
0x18001eb55  mov     r8, rdi; char *
0x18001eb58  mov     rdx, [rbp+phkResult]; HKEY
0x18001eb5c  mov     rcx, r14; struct CDirectMusic *
0x18001eb5f  call    ?EnumerateUMADevice@@YAJPEAVCDirectMusic@@PEAUHKEY__@@PEADPEAUIMMDevice@@KPEAK@Z; EnumerateUMADevice(CDirectMusic *,HKEY__ *,char *,IMMDevice *,ulong,ulong *)
0x18001eb64  inc     ebx
0x18001eb66  cmp     ebx, [rbp+arg_8]
0x18001eb69  jb      short loc_18001EB28
0x18001eb6b  test    rdi, rdi
0x18001eb6e  jz      short loc_18001EB78
0x18001eb70  mov     rcx, rdi; void *
0x18001eb73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eb78  mov     rcx, [rbp+phkResult]; hKey
0x18001eb7c  test    rcx, rcx
0x18001eb7f  jz      short loc_18001EB88
0x18001eb81  call    cs:__imp_RegCloseKey
0x18001eb87  nop
0x18001eb88  mov     rcx, [rbp+var_18]
0x18001eb8c  test    rcx, rcx
0x18001eb8f  jz      short loc_18001EB9E
0x18001eb91  mov     rax, [rcx]
0x18001eb94  mov     rax, [rax+10h]
0x18001eb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb9d  nop
0x18001eb9e  mov     rcx, [rbp+var_28]
0x18001eba2  test    rcx, rcx
0x18001eba5  jz      short loc_18001EBB4
0x18001eba7  mov     rax, [rcx]
0x18001ebaa  mov     rax, [rax+10h]
0x18001ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebb3  nop
0x18001ebb4  mov     rcx, [rbp+var_38]
0x18001ebb8  test    rcx, rcx
0x18001ebbb  jz      short loc_18001EBCA
0x18001ebbd  mov     rax, [rcx]
0x18001ebc0  mov     rax, [rax+10h]
0x18001ebc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebc9  nop
0x18001ebca  mov     rcx, [rbp+var_10]
0x18001ebce  test    rcx, rcx
0x18001ebd1  jz      short loc_18001EBE0
0x18001ebd3  mov     rax, [rcx]
0x18001ebd6  mov     rax, [rax+10h]
0x18001ebda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebdf  nop
0x18001ebe0  mov     eax, esi
0x18001ebe2  mov     rbx, [rsp+70h+arg_0]
0x18001ebea  add     rsp, 70h
0x18001ebee  pop     r15
0x18001ebf0  pop     r14
0x18001ebf2  pop     rdi
0x18001ebf3  pop     rsi
0x18001ebf4  pop     rbp
0x18001ebf5  retn
0x18001ebf6  mov     rdi, [rbp+var_20]
0x18001ebfa  jmp     loc_18001EA4A
```
