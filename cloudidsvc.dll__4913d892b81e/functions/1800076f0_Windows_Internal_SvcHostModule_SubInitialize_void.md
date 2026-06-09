# Windows::Internal::SvcHostModule::SubInitialize(void)

- ea: `0x1800076f0`
- end: `0x18000772b`
- name: `?SubInitialize@SvcHostModule@Internal@Windows@@MEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006d14`
- `0x1800076f0`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x1800076fa`
- `combase!__imp_CoGetSharedServiceId` at `0x1800076fa`

## string_xrefs

- `0x18000770b`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SvcHostModule::SubInitialize(Windows::Internal::SvcHostModule *this)
{
  int SharedServiceId; // eax
  unsigned int v2; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SharedServiceId = CoGetSharedServiceId((char *)this + 56);
  v2 = SharedServiceId;
  if ( SharedServiceId >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19C,
    (int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)SharedServiceId);
  return v2;
}

```

## disassembly

```asm
0x1800076f0  push    rbx; int
0x1800076f2  sub     rsp, 20h
0x1800076f6  add     rcx, 38h ; '8'
0x1800076fa  call    cs:__imp_CoGetSharedServiceId
0x180007700  mov     ebx, eax
0x180007702  test    eax, eax
0x180007704  jns     short loc_180007723
0x180007706  mov     rcx, [rsp+28h]; this
0x18000770b  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180007712  mov     r9d, eax; char *
0x180007715  mov     edx, 19Ch; void *
0x18000771a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000771f  mov     eax, ebx
0x180007721  jmp     short loc_180007725
0x180007723  xor     eax, eax
0x180007725  add     rsp, 20h
0x180007729  pop     rbx
0x18000772a  retn
```
