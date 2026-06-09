# EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)

- ea: `0x1800458f8`
- end: `0x1800459e2`
- name: `?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800115c8`
- `0x180011eb0`
- `0x180045ca0`
- `0x180045cf0`

## callees

- `0x1800458f8`
- `0x180046e70`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x180045951`
- `ADVAPI32!EventActivityIdControl` at `0x1800459be`
- `ADVAPI32!EventActivityIdControl` at `0x180045951`
- `ADVAPI32!EventActivityIdControl` at `0x1800459be`
- `ADVAPI32!EventWrite` at `0x18004599c`
- `ADVAPI32!EventWrite` at `0x18004599c`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(
        __int64 a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  REGHANDLE v4; // rdi
  GUID *p_ActivityId; // r9
  ULONG v7; // r8d
  ULONG v8; // edi
  int v10; // [rsp+20h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+28h] [rbp-28h] BYREF
  int *v12; // [rsp+38h] [rbp-18h]
  __int64 v13; // [rsp+40h] [rbp-10h]

  v4 = Microsoft_Windows_Networking_CorrelationHandle;
  v10 = 0;
  if ( a2->Id == 0xEA61 )
  {
    ActivityId = 0;
    if ( a3 )
      ActivityId = *a3;
    EventActivityIdControl(2u, &ActivityId);
  }
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *(_QWORD *)ActivityId.Data4 = 16;
    *(_QWORD *)&ActivityId.Data1 = &Microsoft_Windows_Networking_ProviderId;
    p_ActivityId = &ActivityId;
    v13 = 4;
    v12 = &v10;
    v7 = 2;
  }
  else
  {
    p_ActivityId = 0;
    v7 = 0;
  }
  v8 = EventWrite(v4, a2, v7, (PEVENT_DATA_DESCRIPTOR)p_ActivityId);
  if ( a2->Id == 0xEA62 )
  {
    ActivityId = 0;
    EventActivityIdControl(2u, &ActivityId);
  }
  return v8;
}

```

## disassembly

```asm
0x1800458f8  mov     [rsp-8+arg_0], rbx
0x1800458fd  mov     [rsp-8+arg_18], rdi
0x180045902  push    rbp
0x180045903  mov     rbp, rsp
0x180045906  sub     rsp, 50h
0x18004590a  mov     rax, cs:__security_cookie
0x180045911  xor     rax, rsp
0x180045914  mov     [rbp+var_8], rax
0x180045918  mov     rdi, cs:Microsoft_Windows_Networking_CorrelationHandle
0x18004591f  mov     eax, 0EA61h
0x180045924  mov     rbx, rdx
0x180045927  mov     [rbp+var_30], 0
0x18004592e  cmp     [rdx], ax
0x180045931  jnz     short loc_180045957
0x180045933  xorps   xmm0, xmm0
0x180045936  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x18004593a  test    r8, r8
0x18004593d  jz      short loc_180045948
0x18004593f  movups  xmm0, xmmword ptr [r8]
0x180045943  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x180045948  lea     rdx, [rbp+ActivityId]; ActivityId
0x18004594c  mov     ecx, 2; ControlCode
0x180045951  call    cs:__imp_EventActivityIdControl
0x180045957  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x18004595d  mov     rdx, rbx; EventDescriptor
0x180045960  mov     rcx, rdi; RegHandle
0x180045963  test    eax, eax
0x180045965  jz      short loc_180045996
0x180045967  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18004596e  mov     qword ptr [rbp+ActivityId.Data4], 10h
0x180045976  mov     qword ptr [rbp+ActivityId.Data1], rax
0x18004597a  lea     r9, [rbp+ActivityId]
0x18004597e  lea     rax, [rbp+var_30]
0x180045982  mov     [rbp+var_10], 4
0x18004598a  mov     [rbp+var_18], rax
0x18004598e  mov     r8d, 2
0x180045994  jmp     short loc_18004599C
0x180045996  xor     r9d, r9d; UserData
0x180045999  xor     r8d, r8d; UserDataCount
0x18004599c  call    cs:__imp_EventWrite
0x1800459a2  mov     edi, eax
0x1800459a4  mov     eax, 0EA62h
0x1800459a9  cmp     [rbx], ax
0x1800459ac  jnz     short loc_1800459C4
0x1800459ae  xorps   xmm0, xmm0
0x1800459b1  lea     rdx, [rbp+ActivityId]; ActivityId
0x1800459b5  mov     ecx, 2; ControlCode
0x1800459ba  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1800459be  call    cs:__imp_EventActivityIdControl
0x1800459c4  mov     eax, edi
0x1800459c6  mov     rcx, [rbp+var_8]
0x1800459ca  xor     rcx, rsp; StackCookie
0x1800459cd  call    __security_check_cookie
0x1800459d2  mov     rbx, [rsp+50h+arg_0]
0x1800459d7  mov     rdi, [rsp+50h+arg_18]
0x1800459dc  add     rsp, 50h
0x1800459e0  pop     rbp
0x1800459e1  retn
```
