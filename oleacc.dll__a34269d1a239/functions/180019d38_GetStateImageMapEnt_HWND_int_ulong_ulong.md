# GetStateImageMapEnt(HWND__ *,int,ulong *,ulong *)

- ea: `0x180019d38`
- end: `0x180019e11`
- name: `?GetStateImageMapEnt@@YAHPEAUHWND__@@HPEAK1@Z`
- size: `217`
- prototype: `__int64 __fastcall(HWND, int, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800048c0`
- `0x180005220`
- `0x1800073b0`
- `0x18000cb40`

## callees

- `0x18000c594`
- `0x180019d38`
- `0x18003c500`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019db0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019db0`
- `USER32!GetPropW` at `0x180019d53`
- `USER32!GetPropW` at `0x180019d53`

## pseudocode

```c
__int64 __fastcall GetStateImageMapEnt(HWND a1, unsigned int a2, unsigned int *a3, unsigned int *a4)
{
  int v9; // ebx
  LPVOID ppv[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !GetPropW(a1, L"MSAAStateImageMapCount") )
    return 0;
  LODWORD(ppv[0]) = 0;
  if ( (int)SameBitness(a1, (int *)ppv) < 0 )
    return 0;
  if ( !LODWORD(ppv[0]) )
  {
    ppv[0] = 0;
    if ( CoCreateInstance(&CLSID_RemoteProxyFactory32, 0, 4u, &IID_IRemoteProxyFactory, ppv) >= 0 && ppv[0] )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, unsigned int *, unsigned int *))(*(_QWORD *)ppv[0] + 64LL))(
             ppv[0],
             (unsigned int)a1,
             a2,
             a3,
             a4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      return v9 == 0;
    }
    return 0;
  }
  return GetStateImageMapEnt_SameBitness(a1);
}

```

## disassembly

```asm
0x180019d38  push    rbx
0x180019d3a  push    rbp
0x180019d3b  push    rsi
0x180019d3c  push    rdi
0x180019d3d  sub     rsp, 48h
0x180019d41  mov     ebp, edx
0x180019d43  mov     rdi, r9
0x180019d46  lea     rdx, aMsaastateimage_0; "MSAAStateImageMapCount"
0x180019d4d  mov     rsi, r8
0x180019d50  mov     rbx, rcx
0x180019d53  call    cs:__imp_GetPropW
0x180019d59  test    rax, rax
0x180019d5c  jnz     short loc_180019D69
0x180019d5e  xor     eax, eax
0x180019d60  add     rsp, 48h
0x180019d64  pop     rdi
0x180019d65  pop     rsi
0x180019d66  pop     rbp
0x180019d67  pop     rbx
0x180019d68  retn
0x180019d69  lea     rdx, [rsp+68h+var_38]; int *
0x180019d6e  mov     dword ptr [rsp+68h+var_38], 0
0x180019d76  mov     rcx, rbx; HWND
0x180019d79  call    ?SameBitness@@YAJPEAUHWND__@@PEAH@Z; SameBitness(HWND__ *,int *)
0x180019d7e  test    eax, eax
0x180019d80  js      short loc_180019D5E
0x180019d82  cmp     dword ptr [rsp+68h+var_38], 0
0x180019d87  jnz     short loc_180019DFC
0x180019d89  xor     edx, edx; pUnkOuter
0x180019d8b  mov     [rsp+68h+var_38], 0
0x180019d94  lea     rax, [rsp+68h+var_38]
0x180019d99  lea     r9, IID_IRemoteProxyFactory; riid
0x180019da0  mov     [rsp+68h+ppv], rax; ppv
0x180019da5  lea     rcx, CLSID_RemoteProxyFactory32; rclsid
0x180019dac  lea     r8d, [rdx+4]; dwClsContext
0x180019db0  call    cs:__imp_CoCreateInstance
0x180019db6  test    eax, eax
0x180019db8  js      short loc_180019D5E
0x180019dba  mov     rcx, [rsp+68h+var_38]
0x180019dbf  test    rcx, rcx
0x180019dc2  jz      short loc_180019D5E
0x180019dc4  mov     rax, [rcx]
0x180019dc7  mov     edx, ebx
0x180019dc9  mov     r9, rsi
0x180019dcc  mov     [rsp+68h+ppv], rdi
0x180019dd1  mov     r8d, ebp
0x180019dd4  mov     rax, [rax+40h]
0x180019dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ddd  mov     rcx, [rsp+68h+var_38]
0x180019de2  mov     ebx, eax
0x180019de4  mov     rdx, [rcx]
0x180019de7  mov     rax, [rdx+10h]
0x180019deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019df0  xor     eax, eax
0x180019df2  test    ebx, ebx
0x180019df4  setz    al
0x180019df7  jmp     loc_180019D60
0x180019dfc  mov     r9, rdi
0x180019dff  mov     r8, rsi
0x180019e02  mov     edx, ebp
0x180019e04  mov     rcx, rbx; HWND
0x180019e07  call    GetStateImageMapEnt_SameBitness
0x180019e0c  jmp     loc_180019D60
```
