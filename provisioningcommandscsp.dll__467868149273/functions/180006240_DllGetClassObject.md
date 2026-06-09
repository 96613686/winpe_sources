# DllGetClassObject

- ea: `0x180006240`
- end: `0x1800062f8`
- name: `DllGetClassObject`
- size: `184`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800016b4`
- `0x180006240`
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
    v6 = (_QWORD *)*((_QWORD *)&off_18000F0A8 + 2 * v5);
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
  v8[2] = (char *)&off_18000F0A8 + 16 * v5;
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
0x180006240  push    rbx
0x180006242  push    rbp
0x180006243  push    rsi
0x180006244  push    rdi
0x180006245  push    r15
0x180006247  sub     rsp, 20h
0x18000624b  mov     rsi, r8
0x18000624e  mov     rbp, rdx
0x180006251  test    r8, r8
0x180006254  jz      short loc_18000625D
0x180006256  mov     qword ptr [r8], 0
0x18000625d  xor     ebx, ebx
0x18000625f  lea     r15, off_18000F0A8
0x180006266  mov     eax, ebx
0x180006268  add     rax, rax
0x18000626b  mov     rdx, [r15+rax*8]
0x18000626f  mov     rax, [rdx]
0x180006272  cmp     rax, [rcx]
0x180006275  jnz     short loc_180006281
0x180006277  mov     rax, [rdx+8]
0x18000627b  cmp     rax, [rcx+8]
0x18000627f  jz      short loc_180006291
0x180006281  inc     ebx
0x180006283  cmp     ebx, 1
0x180006286  jl      short loc_180006266
0x180006288  jnz     short loc_180006291
0x18000628a  mov     eax, 80040111h
0x18000628f  jmp     short loc_1800062EC
0x180006291  mov     ecx, 18h; Size
0x180006296  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000629b  mov     rdi, rax
0x18000629e  test    rax, rax
0x1800062a1  jz      short loc_1800062E7
0x1800062a3  lea     rax, ??_7CProvisioningCommandsClassFactory@@6B@; const CProvisioningCommandsClassFactory::`vftable'
0x1800062aa  mov     ecx, ebx
0x1800062ac  shl     rcx, 4
0x1800062b0  mov     r8, rsi
0x1800062b3  add     rcx, r15
0x1800062b6  mov     [rdi], rax
0x1800062b9  mov     rax, [rax]
0x1800062bc  mov     rdx, rbp
0x1800062bf  mov     [rdi+10h], rcx
0x1800062c3  mov     rcx, rdi
0x1800062c6  mov     dword ptr [rdi+8], 1
0x1800062cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d2  mov     rcx, [rdi]
0x1800062d5  mov     ebx, eax
0x1800062d7  mov     rax, [rcx+10h]
0x1800062db  mov     rcx, rdi
0x1800062de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e3  mov     eax, ebx
0x1800062e5  jmp     short loc_1800062EC
0x1800062e7  mov     eax, 8007000Eh
0x1800062ec  add     rsp, 20h
0x1800062f0  pop     r15
0x1800062f2  pop     rdi
0x1800062f3  pop     rsi
0x1800062f4  pop     rbp
0x1800062f5  pop     rbx
0x1800062f6  retn
```
