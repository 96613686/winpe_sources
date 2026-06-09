# DllGetClassObject

- ea: `0x1800019d0`
- end: `0x180001a23`
- name: `DllGetClassObject`
- size: `83`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800019d0`
- `0x180012010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v3; // r9
  _QWORD *v4; // r11

  v3 = 0;
  while ( 1 )
  {
    v4 = *(&g_aclscache + 2 * v3);
    if ( *(_QWORD *)&rclsid->Data1 == *v4 && *(_QWORD *)rclsid->Data4 == v4[1] )
      break;
    if ( (unsigned __int64)++v3 >= 7 )
    {
      *ppv = 0;
      return -2147221231;
    }
  }
  return (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))*(&g_aclscache + 2 * v3 + 1))(
           *(&g_aclscache + 2 * v3 + 1),
           riid,
           ppv);
}

```

## disassembly

```asm
0x1800019d0  push    rbx
0x1800019d2  mov     r10, rcx
0x1800019d5  lea     rbx, ?g_aclscache@@3PAUCLSCACHE@@A; CLSCACHE near * g_aclscache
0x1800019dc  xor     r9d, r9d
0x1800019df  mov     rax, [r10]
0x1800019e2  mov     rcx, r9
0x1800019e5  add     rcx, rcx
0x1800019e8  mov     r11, [rbx+rcx*8]
0x1800019ec  cmp     rax, [r11]
0x1800019ef  jnz     short loc_1800019FB
0x1800019f1  mov     rax, [r10+8]
0x1800019f5  cmp     rax, [r11+8]
0x1800019f9  jz      short loc_180001A12
0x1800019fb  inc     r9
0x1800019fe  cmp     r9, 7
0x180001a02  jb      short loc_1800019DF
0x180001a04  mov     qword ptr [r8], 0
0x180001a0b  mov     eax, 80040111h
0x180001a10  pop     rbx
0x180001a11  retn
0x180001a12  mov     rcx, [rbx+rcx*8+8]
0x180001a17  mov     rax, [rcx]
0x180001a1a  mov     rax, [rax]
0x180001a1d  pop     rbx
0x180001a1e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
