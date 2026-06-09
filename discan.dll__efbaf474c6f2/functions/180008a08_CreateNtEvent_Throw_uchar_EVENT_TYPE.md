# CreateNtEvent_Throw(uchar,_EVENT_TYPE)

- ea: `0x180008a08`
- end: `0x180008a64`
- name: `?CreateNtEvent_Throw@@YAPEAXEW4_EVENT_TYPE@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(BOOLEAN, EVENT_TYPE)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180020d90`

## callees

- `0x180003640`
- `0x1800088a4`
- `0x180008a08`
- `0x180009088`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x180008a2e`
- `ntdll!NtCreateEvent` at `0x180008a2e`

## pseudocode

```c
__int64 __fastcall CreateNtEvent_Throw(BOOLEAN a1, EVENT_TYPE a2)
{
  NTSTATUS v2; // eax
  __int64 v3; // rbx
  void *v5; // [rsp+30h] [rbp-18h] BYREF
  int v6; // [rsp+38h] [rbp-10h]
  char v7; // [rsp+3Ch] [rbp-Ch]

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v2 = NtCreateEvent(&v5, 0x1F0003u, 0, a2, a1);
  if ( v2 < 0 )
    ATL::AtlThrowImpl(v2 | 0x10000000);
  v3 = CHandleT<void *,NtHandleTrait>::Detach(&v5);
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&v5);
  return v3;
}

```

## disassembly

```asm
0x180008a08  mov     rax, rsp
0x180008a0b  push    rbx
0x180008a0c  sub     rsp, 40h
0x180008a10  xor     ebx, ebx
0x180008a12  mov     [rax-18h], rbx
0x180008a16  mov     [rax-10h], ebx
0x180008a19  mov     [rax-0Ch], bl
0x180008a1c  mov     [rax-28h], cl
0x180008a1f  mov     r9d, edx; EventType
0x180008a22  xor     r8d, r8d; ObjectAttributes
0x180008a25  mov     edx, 1F0003h; DesiredAccess
0x180008a2a  lea     rcx, [rax-18h]; EventHandle
0x180008a2e  call    cs:__imp_NtCreateEvent
0x180008a34  test    eax, eax
0x180008a36  jns     short loc_180008A44
0x180008a38  bts     eax, 1Ch
0x180008a3c  mov     ecx, eax; int
0x180008a3e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008a44  lea     rcx, [rsp+48h+var_18]
0x180008a49  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x180008a4e  mov     rbx, rax
0x180008a51  lea     rcx, [rsp+48h+var_18]
0x180008a56  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180008a5b  mov     rax, rbx
0x180008a5e  add     rsp, 40h
0x180008a62  pop     rbx
0x180008a63  retn
```
