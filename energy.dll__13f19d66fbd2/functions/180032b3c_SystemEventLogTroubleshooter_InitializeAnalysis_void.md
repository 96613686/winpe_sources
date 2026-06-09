# SystemEventLogTroubleshooter::InitializeAnalysis(void)

- ea: `0x180032b3c`
- end: `0x180032c1a`
- name: `?InitializeAnalysis@SystemEventLogTroubleshooter@@QEAAKXZ`
- size: `222`
- prototype: `unsigned int __fastcall(SystemEventLogTroubleshooter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b130`

## callees

- `0x180032b3c`
- `0x180032c20`
- `0x18008c4d8`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032bfd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032c0f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032bfd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b96`

## string_xrefs

- `0x180032b7c`: `<QueryList>  <Query Path='System'>    <Select>Event/System[EventID=1]</Select>    <Select>Event/System[EventID=12]</Select>    <Select>Event/System[EventID=13]</Select>    <Select>Event/System[EventID=20]</Select>    <Select>Event/System[EventID=41]</Select>    <Select>Event/System[EventID=42]</Select>    <Select>Event/System[EventID=105]</Select>    <Select>Event/System[EventID=107]</Select>    <Select>Event/System[EventID=109]</Select>    <Select>Event/System[EventID=506]</Select>    <Select>E`

## pseudocode

```c
__int64 __fastcall SystemEventLogTroubleshooter::InitializeAnalysis(SystemEventLogTroubleshooter *this)
{
  struct _EVT_VARIANT *v1; // rbx
  unsigned int EventLogDll; // edi
  void *v5; // rdx
  unsigned int QueryStatusProperty; // eax
  _DWORD *v7; // rsi
  unsigned int v8; // eax
  __int64 i; // rcx
  struct _EVT_VARIANT *v10; // [rsp+58h] [rbp+10h] BYREF
  void *Block; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  Block = 0;
  v10 = 0;
  EventLogDll = LoadEventLogDll();
  if ( !EventLogDll )
  {
    *((_QWORD *)this + 1) = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, __int64))PEvtQuery)(
                              0,
                              0,
                              L"<QueryList>  <Query Path='System'>    <Select>Event/System[EventID=1]</Select>    <Select>"
                               "Event/System[EventID=12]</Select>    <Select>Event/System[EventID=13]</Select>    <Select"
                               ">Event/System[EventID=20]</Select>    <Select>Event/System[EventID=41]</Select>    <Selec"
                               "t>Event/System[EventID=42]</Select>    <Select>Event/System[EventID=105]</Select>    <Sel"
                               "ect>Event/System[EventID=107]</Select>    <Select>Event/System[EventID=109]</Select>    <"
                               "Select>Event/System[EventID=506]</Select>    <Select>Event/System[EventID=507]</Select>  "
                               "  <Select>Event/System[EventID=521]</Select>    <Select>Event/System[EventID=566]</Select"
                               ">    <Select>Event/System[EventID=1074]</Select>  </Query>  <Query Path='Microsoft-Window"
                               "s-Kernel-Boot/Operational'>    <Select>*[System[(Level=2) and (EventID=158)]]</Select>  <"
                               "/Query></QueryList>",
                              257);
    EventLogDll = GetLastError();
    if ( !EventLogDll )
    {
      v5 = (void *)*((_QWORD *)this + 1);
      if ( v5 )
      {
        QueryStatusProperty = GetQueryStatusProperty(EvtQueryNames, v5, (struct _EVT_VARIANT **)&Block);
        v7 = Block;
        EventLogDll = QueryStatusProperty;
        if ( !QueryStatusProperty )
        {
          v8 = GetQueryStatusProperty(EvtQueryStatuses, *((void **)this + 1), &v10);
          v1 = v10;
          EventLogDll = v8;
          if ( !v8 )
          {
            for ( i = 0; (unsigned int)i < v7[2]; i = (unsigned int)(i + 1) )
            {
              if ( *(_DWORD *)(v10->Int64Val + 4 * i) )
              {
                EventLogDll = *(_DWORD *)(v10->Int64Val + 4 * i);
                break;
              }
            }
          }
        }
        if ( v7 )
          free(v7);
        if ( v1 )
          free(v1);
      }
    }
  }
  return EventLogDll;
}

```

## disassembly

```asm
0x180032b3c  mov     [rsp+arg_0], rbx
0x180032b41  push    rbp
0x180032b42  push    rsi
0x180032b43  push    rdi
0x180032b44  sub     rsp, 30h
0x180032b48  xor     ebx, ebx
0x180032b4a  mov     [rsp+48h+Block], 0
0x180032b53  mov     [rsp+48h+arg_8], rbx
0x180032b58  mov     rbp, rcx
0x180032b5b  call    ?LoadEventLogDll@@YAKXZ; LoadEventLogDll(void)
0x180032b60  mov     edi, eax
0x180032b62  test    eax, eax
0x180032b64  jz      short loc_180032B75
0x180032b66  mov     rbx, [rsp+48h+arg_0]
0x180032b6b  mov     eax, edi
0x180032b6d  add     rsp, 30h
0x180032b71  pop     rdi
0x180032b72  pop     rsi
0x180032b73  pop     rbp
0x180032b74  retn
0x180032b75  mov     rax, cs:?PEvtQuery@@3P6APEAXPEAXPEBG1K@ZEA; void * (*PEvtQuery)(void *,ushort const *,ushort const *,ulong)
0x180032b7c  lea     r8, aQuerylistQuery; "<QueryList>  <Query Path='System'>    <"...
0x180032b83  mov     r9d, 101h
0x180032b89  xor     edx, edx
0x180032b8b  xor     ecx, ecx
0x180032b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b92  mov     [rbp+8], rax
0x180032b96  call    cs:__imp_GetLastError
0x180032b9c  mov     edi, eax
0x180032b9e  test    eax, eax
0x180032ba0  jnz     short loc_180032B66
0x180032ba2  mov     rdx, [rbp+8]; void *
0x180032ba6  test    rdx, rdx
0x180032ba9  jz      short loc_180032B66
0x180032bab  lea     r8, [rsp+48h+Block]; struct _EVT_VARIANT **
0x180032bb0  xor     ecx, ecx; enum _EVT_QUERY_PROPERTY_ID
0x180032bb2  call    ?GetQueryStatusProperty@@YAKW4_EVT_QUERY_PROPERTY_ID@@PEAXAEAPEAU_EVT_VARIANT@@@Z; GetQueryStatusProperty(_EVT_QUERY_PROPERTY_ID,void *,_EVT_VARIANT * &)
0x180032bb7  mov     rsi, [rsp+48h+Block]
0x180032bbc  mov     edi, eax
0x180032bbe  test    eax, eax
0x180032bc0  jnz     short loc_180032BF5
0x180032bc2  mov     rdx, [rbp+8]; void *
0x180032bc6  lea     r8, [rsp+48h+arg_8]; struct _EVT_VARIANT **
0x180032bcb  lea     ecx, [rax+1]; enum _EVT_QUERY_PROPERTY_ID
0x180032bce  call    ?GetQueryStatusProperty@@YAKW4_EVT_QUERY_PROPERTY_ID@@PEAXAEAPEAU_EVT_VARIANT@@@Z; GetQueryStatusProperty(_EVT_QUERY_PROPERTY_ID,void *,_EVT_VARIANT * &)
0x180032bd3  mov     rbx, [rsp+48h+arg_8]
0x180032bd8  mov     edi, eax
0x180032bda  test    eax, eax
0x180032bdc  jnz     short loc_180032BF5
0x180032bde  xor     ecx, ecx
0x180032be0  cmp     ecx, [rsi+8]
0x180032be3  jnb     short loc_180032BF5
0x180032be5  mov     rax, [rbx]
0x180032be8  cmp     dword ptr [rax+rcx*4], 0
0x180032bec  jnz     short loc_180032BF2
0x180032bee  inc     ecx
0x180032bf0  jmp     short loc_180032BE0
0x180032bf2  mov     edi, [rax+rcx*4]
0x180032bf5  test    rsi, rsi
0x180032bf8  jz      short loc_180032C03
0x180032bfa  mov     rcx, rsi; Block
0x180032bfd  call    cs:__imp_free
0x180032c03  test    rbx, rbx
0x180032c06  jz      loc_180032B66
0x180032c0c  mov     rcx, rbx; Block
0x180032c0f  call    cs:__imp_free
0x180032c15  jmp     loc_180032B66
```
