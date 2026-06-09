# EnableMLangSupport(void * *)

- ea: `0x1800bd8b8`
- end: `0x1800bd929`
- name: `?EnableMLangSupport@@YAJPEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004db10`
- `0x1800bc878`

## callees

- `0x1800bd8b8`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800bd8ed`
- `ole32!CoCreateInstance` at `0x1800bd916`
- `ole32!CoCreateInstance` at `0x1800bd8ed`
- `ole32!CoCreateInstance` at `0x1800bd916`

## pseudocode

```c
int __fastcall EnableMLangSupport(LPVOID *ppv)
{
  int result; // eax

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  result = CoCreateInstance(&CLSID_CMultiLanguage, 0, 3u, &IID_IMultiLanguage2, ppv);
  if ( result < 0 )
    return CoCreateInstance(&CLSID_CMultiLanguage, 0, 3u, &IID_IMultiLanguage, ppv);
  return result;
}

```

## disassembly

```asm
0x1800bd8b8  push    rbx
0x1800bd8ba  sub     rsp, 30h
0x1800bd8be  mov     rbx, rcx
0x1800bd8c1  test    rcx, rcx
0x1800bd8c4  jnz     short loc_1800BD8CD
0x1800bd8c6  mov     eax, 80070057h
0x1800bd8cb  jmp     short loc_1800BD922
0x1800bd8cd  xor     edx, edx; pUnkOuter
0x1800bd8cf  mov     qword ptr [rcx], 0
0x1800bd8d6  lea     r9, IID_IMultiLanguage2; riid
0x1800bd8dd  mov     [rsp+38h+ppv], rbx; ppv
0x1800bd8e2  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1800bd8e9  lea     r8d, [rdx+3]; dwClsContext
0x1800bd8ed  call    cs:__imp_CoCreateInstance
0x1800bd8f4  nop     dword ptr [rax+rax+00h]
0x1800bd8f9  test    eax, eax
0x1800bd8fb  jns     short loc_1800BD922
0x1800bd8fd  xor     edx, edx; pUnkOuter
0x1800bd8ff  mov     [rsp+38h+ppv], rbx; ppv
0x1800bd904  lea     r9, IID_IMultiLanguage; riid
0x1800bd90b  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1800bd912  lea     r8d, [rdx+3]; dwClsContext
0x1800bd916  call    cs:__imp_CoCreateInstance
0x1800bd91d  nop     dword ptr [rax+rax+00h]
0x1800bd922  add     rsp, 30h
0x1800bd926  pop     rbx
0x1800bd927  retn
```
