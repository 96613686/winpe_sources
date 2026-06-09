# DllGetClassObject

- ea: `0x180005f70`
- end: `0x180006027`
- name: `DllGetClassObject`
- size: `183`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800016a4`
- `0x180005f70`
- `0x18000e010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rdx
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  HRESULT v10; // ebx

  if ( ppv )
    *ppv = 0;
  v5 = 0;
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)&off_18000F0B0 + 2 * v5);
    if ( *v6 == *(_QWORD *)&rclsid->Data1 && v6[1] == *(_QWORD *)rclsid->Data4 )
      break;
    if ( (int)++v5 >= 1 )
    {
      if ( v5 == 1 )
        return -2147221231;
      break;
    }
  }
  v8 = operator new(0x18u);
  v9 = v8;
  if ( !v8 )
    return -2147024882;
  *v8 = &CProvisioningCommandsClassFactory::`vftable';
  v8[2] = (char *)&off_18000F0B0 + 16 * v5;
  *((_DWORD *)v8 + 2) = 1;
  v10 = ((__int64 (__fastcall *)(_QWORD *, const IID *const, LPVOID *))CProvisioningCommandsClassFactory::`vftable')(
          v8,
          riid,
          ppv);
  (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  return v10;
}

```

## disassembly

```asm
0x180005f70  push    rbx
0x180005f72  push    rbp
0x180005f73  push    rsi
0x180005f74  push    rdi
0x180005f75  push    r15
0x180005f77  sub     rsp, 20h
0x180005f7b  mov     rsi, r8
0x180005f7e  mov     rbp, rdx
0x180005f81  test    r8, r8
0x180005f84  jz      short loc_180005F8D
0x180005f86  mov     qword ptr [r8], 0
0x180005f8d  xor     ebx, ebx
0x180005f8f  lea     r15, off_18000F0B0
0x180005f96  mov     eax, ebx
0x180005f98  add     rax, rax
0x180005f9b  mov     rdx, [r15+rax*8]
0x180005f9f  mov     rax, [rdx]
0x180005fa2  cmp     rax, [rcx]
0x180005fa5  jnz     short loc_180005FB1
0x180005fa7  mov     rax, [rdx+8]
0x180005fab  cmp     rax, [rcx+8]
0x180005faf  jz      short loc_180005FC1
0x180005fb1  inc     ebx
0x180005fb3  cmp     ebx, 1
0x180005fb6  jl      short loc_180005F96
0x180005fb8  jnz     short loc_180005FC1
0x180005fba  mov     eax, 80040111h
0x180005fbf  jmp     short loc_18000601C
0x180005fc1  mov     ecx, 18h; Size
0x180005fc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fcb  mov     rdi, rax
0x180005fce  test    rax, rax
0x180005fd1  jz      short loc_180006017
0x180005fd3  lea     rax, ??_7CProvisioningCommandsClassFactory@@6B@; const CProvisioningCommandsClassFactory::`vftable'
0x180005fda  mov     ecx, ebx
0x180005fdc  shl     rcx, 4
0x180005fe0  mov     r8, rsi
0x180005fe3  add     rcx, r15
0x180005fe6  mov     [rdi], rax
0x180005fe9  mov     rax, [rax]
0x180005fec  mov     rdx, rbp
0x180005fef  mov     [rdi+10h], rcx
0x180005ff3  mov     rcx, rdi
0x180005ff6  mov     dword ptr [rdi+8], 1
0x180005ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006002  mov     rcx, [rdi]
0x180006005  mov     ebx, eax
0x180006007  mov     rax, [rcx+10h]
0x18000600b  mov     rcx, rdi
0x18000600e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006013  mov     eax, ebx
0x180006015  jmp     short loc_18000601C
0x180006017  mov     eax, 8007000Eh
0x18000601c  add     rsp, 20h
0x180006020  pop     r15
0x180006022  pop     rdi
0x180006023  pop     rsi
0x180006024  pop     rbp
0x180006025  pop     rbx
0x180006026  retn
```
