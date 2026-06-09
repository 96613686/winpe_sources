# CBaseInputPin::GetAllocator(IMemAllocator * *)

- ea: `0x180026ff0`
- end: `0x18002708b`
- name: `?GetAllocator@CBaseInputPin@@UEAAJPEAPEAUIMemAllocator@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(CBaseInputPin *__hidden this, struct IMemAllocator **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180026ff0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027045`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027072`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027016`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027016`

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
0x180026ff0  push    rbx
0x180026ff2  push    rsi
0x180026ff3  push    rdi
0x180026ff4  push    r14
0x180026ff6  sub     rsp, 38h
0x180026ffa  mov     r14, rdx
0x180026ffd  mov     rbx, rcx
0x180027000  test    rdx, rdx
0x180027003  jnz     short loc_18002700C
0x180027005  mov     eax, 80004003h
0x18002700a  jmp     short loc_180027080
0x18002700c  mov     rdi, [rcx-98h]
0x180027013  mov     rcx, rdi; lpCriticalSection
0x180027016  call    cs:__imp_EnterCriticalSection
0x18002701d  nop     dword ptr [rax+rax+00h]
0x180027022  add     rbx, 8
0x180027026  cmp     qword ptr [rbx], 0
0x18002702a  jnz     short loc_180027057
0x18002702c  xor     edx, edx; pUnkOuter
0x18002702e  mov     [rsp+58h+ppv], rbx; ppv
0x180027033  lea     r9, IID_IMemAllocator; riid
0x18002703a  lea     rcx, CLSID_MemoryAllocator; rclsid
0x180027041  lea     r8d, [rdx+1]; dwClsContext
0x180027045  call    cs:__imp_CoCreateInstance
0x18002704c  nop     dword ptr [rax+rax+00h]
0x180027051  mov     esi, eax
0x180027053  test    eax, eax
0x180027055  js      short loc_18002706F
0x180027057  mov     rax, [rbx]
0x18002705a  mov     [r14], rax
0x18002705d  mov     rcx, [rbx]
0x180027060  mov     rax, [rcx]
0x180027063  mov     rax, [rax+8]
0x180027067  call    cs:__guard_dispatch_icall_fptr
0x18002706d  xor     esi, esi
0x18002706f  mov     rcx, rdi; lpCriticalSection
0x180027072  call    cs:__imp_LeaveCriticalSection
0x180027079  nop     dword ptr [rax+rax+00h]
0x18002707e  mov     eax, esi
0x180027080  add     rsp, 38h
0x180027084  pop     r14
0x180027086  pop     rdi
0x180027087  pop     rsi
0x180027088  pop     rbx
0x180027089  retn
```
