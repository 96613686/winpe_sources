# CBaseInputPin::GetAllocator(IMemAllocator * *)

- ea: `0x180004a00`
- end: `0x180004a87`
- name: `?GetAllocator@CBaseInputPin@@UEAAJPEAPEAUIMemAllocator@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(CBaseInputPin *__hidden this, struct IMemAllocator **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b610`

## callees

- `0x180004a00`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004a26`
- `KERNEL32!EnterCriticalSection` at `0x180004a26`
- `KERNEL32!LeaveCriticalSection` at `0x180004a75`
- `KERNEL32!LeaveCriticalSection` at `0x180004a75`
- `ole32!CoCreateInstance` at `0x180004a4f`
- `ole32!CoCreateInstance` at `0x180004a4f`

## pseudocode

```c
__int64 __fastcall CBaseInputPin::GetAllocator(CBaseInputPin *this, LPVOID *a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  LPVOID *ppv; // rbx
  HRESULT Instance; // esi

  if ( !a2 )
    return 2147500035LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this - 19);
  EnterCriticalSection(v5);
  ppv = (LPVOID *)((char *)this + 8);
  if ( *ppv || (Instance = CoCreateInstance(&CLSID_MemoryAllocator, 0, 1u, &IID_IMemAllocator, ppv), Instance >= 0) )
  {
    *a2 = *ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 8LL))(*ppv);
    Instance = 0;
  }
  LeaveCriticalSection(v5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180004a00  push    rbx
0x180004a02  push    rsi
0x180004a03  push    rdi
0x180004a04  push    r14
0x180004a06  sub     rsp, 38h
0x180004a0a  mov     r14, rdx
0x180004a0d  mov     rbx, rcx
0x180004a10  test    rdx, rdx
0x180004a13  jnz     short loc_180004A1C
0x180004a15  mov     eax, 80004003h
0x180004a1a  jmp     short loc_180004A7D
0x180004a1c  mov     rdi, [rcx-98h]
0x180004a23  mov     rcx, rdi; lpCriticalSection
0x180004a26  call    cs:__imp_EnterCriticalSection
0x180004a2c  add     rbx, 8
0x180004a30  cmp     qword ptr [rbx], 0
0x180004a34  jnz     short loc_180004A5B
0x180004a36  xor     edx, edx; pUnkOuter
0x180004a38  mov     [rsp+58h+ppv], rbx; ppv
0x180004a3d  lea     r9, IID_IMemAllocator; riid
0x180004a44  lea     rcx, CLSID_MemoryAllocator; rclsid
0x180004a4b  lea     r8d, [rdx+1]; dwClsContext
0x180004a4f  call    cs:__imp_CoCreateInstance
0x180004a55  mov     esi, eax
0x180004a57  test    eax, eax
0x180004a59  js      short loc_180004A72
0x180004a5b  mov     rax, [rbx]
0x180004a5e  mov     [r14], rax
0x180004a61  mov     rcx, [rbx]
0x180004a64  mov     rax, [rcx]
0x180004a67  mov     rax, [rax+8]
0x180004a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a70  xor     esi, esi
0x180004a72  mov     rcx, rdi; lpCriticalSection
0x180004a75  call    cs:__imp_LeaveCriticalSection
0x180004a7b  mov     eax, esi
0x180004a7d  add     rsp, 38h
0x180004a81  pop     r14
0x180004a83  pop     rdi
0x180004a84  pop     rsi
0x180004a85  pop     rbx
0x180004a86  retn
```
