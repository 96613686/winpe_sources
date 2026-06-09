# RunTimeInitializer::AtStop(OnStopCallback &)

- ea: `0x180030638`
- end: `0x18003071c`
- name: `?AtStop@RunTimeInitializer@@SAXAEAVOnStopCallback@@@Z`
- size: `228`
- prototype: `void __fastcall(struct OnStopCallback *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fa28`

## callees

- `0x180003406`
- `0x180030638`
- `0x180032550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180030664`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180030664`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030645`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030645`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030710`

## string_xrefs

- `0x1800306bc`: `create an OnStopCallback object while RunTimeInitializer has not started yet`

## pseudocode

```c
void __fastcall RunTimeInitializer::AtStop(struct OnStopCallback *a1)
{
  __int64 v1; // rax
  const char *v2; // rax
  __int64 *v3; // rcx
  struct OnStopCallback *i; // rax

  EnterCriticalSection(&GlobalLockSentry::lock);
  if ( RunTimeInitializer::refCount <= 0 )
  {
    v1 = __RTtypeid(&off_18004D228);
    v2 = (const char *)_std_type_info_name(v1 + 8, &__type_info_root_node);
    VerifierStop(
      3u,
      "create an OnStopCallback object while RunTimeInitializer has not started yet",
      0,
      v2,
      0,
      0,
      0,
      0,
      0,
      0);
  }
  v3 = (__int64 *)&RunTimeInitializer::atStop;
  for ( i = RunTimeInitializer::atStop; i; i = (struct OnStopCallback *)*((_QWORD *)i + 1) )
  {
    if ( *((_DWORD *)i + 4) >= (int)qword_18004D238 )
      break;
    v3 = (__int64 *)((char *)i + 8);
  }
  qword_18004D230 = *v3;
  *v3 = (__int64)&off_18004D228;
  LeaveCriticalSection(&GlobalLockSentry::lock);
}

```

## disassembly

```asm
0x180030638  push    rdi
0x18003063a  sub     rsp, 50h
0x18003063e  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030645  call    cs:__imp_EnterCriticalSection
0x18003064c  nop     dword ptr [rax+rax+00h]
0x180030651  lea     rdi, off_18004D228
0x180030658  cmp     cs:?refCount@RunTimeInitializer@@0HA, 0; int RunTimeInitializer::refCount
0x18003065f  jg      short loc_1800306CC
0x180030661  mov     rcx, rdi
0x180030664  call    cs:__imp___RTtypeid
0x18003066b  nop     dword ptr [rax+rax+00h]
0x180030670  lea     rcx, [rax+8]
0x180030674  lea     rdx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x18003067b  call    __std_type_info_name
0x180030680  mov     [rsp+58h+var_10], 0; char *
0x180030689  mov     [rsp+58h+var_18], 0; unsigned __int64
0x180030692  mov     [rsp+58h+var_20], 0; char *
0x18003069b  mov     [rsp+58h+var_28], 0; unsigned __int64
0x1800306a4  mov     [rsp+58h+var_30], 0; char *
0x1800306ad  mov     [rsp+58h+var_38], 0; unsigned __int64
0x1800306b6  mov     r9, rax; char *
0x1800306b9  xor     r8d, r8d; unsigned __int64
0x1800306bc  lea     rdx, aCreateAnOnstop; "create an OnStopCallback object while R"...
0x1800306c3  lea     ecx, [r8+3]; unsigned int
0x1800306c7  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x1800306cc  lea     rcx, ?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x1800306d3  mov     rax, cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x1800306da  test    rax, rax
0x1800306dd  jz      short loc_1800306F7
0x1800306df  mov     rdx, cs:qword_18004D238
0x1800306e6  cmp     [rax+10h], edx
0x1800306e9  jge     short loc_1800306F7
0x1800306eb  lea     rcx, [rax+8]
0x1800306ef  mov     rax, [rcx]
0x1800306f2  test    rax, rax
0x1800306f5  jnz     short loc_1800306E6
0x1800306f7  mov     rax, [rcx]
0x1800306fa  mov     cs:qword_18004D230, rax
0x180030701  mov     [rcx], rdi
0x180030704  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION GlobalLockSentry::lock
0x18003070b  add     rsp, 50h
0x18003070f  pop     rdi
0x180030710  jmp     cs:__imp_LeaveCriticalSection
```
