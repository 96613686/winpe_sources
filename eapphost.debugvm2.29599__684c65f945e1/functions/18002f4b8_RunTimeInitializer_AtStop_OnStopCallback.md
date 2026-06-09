# RunTimeInitializer::AtStop(OnStopCallback &)

- ea: `0x18002f4b8`
- end: `0x18002f58b`
- name: `?AtStop@RunTimeInitializer@@SAXAEAVOnStopCallback@@@Z`
- size: `211`
- prototype: `void __fastcall(struct OnStopCallback *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f3f8`

## callees

- `0x180003376`
- `0x18002f4b8`
- `0x180031368`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18002f4de`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18002f4de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f4c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f4c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f584`

## string_xrefs

- `0x18002f530`: `create an OnStopCallback object while RunTimeInitializer has not started yet`

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
    v1 = __RTtypeid(&off_18004C120);
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
    if ( *((_DWORD *)i + 4) >= (int)qword_18004C130 )
      break;
    v3 = (__int64 *)((char *)i + 8);
  }
  qword_18004C128 = *v3;
  *v3 = (__int64)&off_18004C120;
  LeaveCriticalSection(&GlobalLockSentry::lock);
}

```

## disassembly

```asm
0x18002f4b8  push    rdi
0x18002f4ba  sub     rsp, 50h
0x18002f4be  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f4c5  call    cs:__imp_EnterCriticalSection
0x18002f4cb  lea     rdi, off_18004C120
0x18002f4d2  cmp     cs:?refCount@RunTimeInitializer@@0HA, 0; int RunTimeInitializer::refCount
0x18002f4d9  jg      short loc_18002F540
0x18002f4db  mov     rcx, rdi
0x18002f4de  call    cs:__imp___RTtypeid
0x18002f4e4  lea     rcx, [rax+8]
0x18002f4e8  lea     rdx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x18002f4ef  call    __std_type_info_name
0x18002f4f4  mov     [rsp+58h+var_10], 0; char *
0x18002f4fd  mov     [rsp+58h+var_18], 0; unsigned __int64
0x18002f506  mov     [rsp+58h+var_20], 0; char *
0x18002f50f  mov     [rsp+58h+var_28], 0; unsigned __int64
0x18002f518  mov     [rsp+58h+var_30], 0; char *
0x18002f521  mov     [rsp+58h+var_38], 0; unsigned __int64
0x18002f52a  mov     r9, rax; char *
0x18002f52d  xor     r8d, r8d; unsigned __int64
0x18002f530  lea     rdx, aCreateAnOnstop; "create an OnStopCallback object while R"...
0x18002f537  lea     ecx, [r8+3]; unsigned int
0x18002f53b  call    ?VerifierStop@@YAXIPEBD_K0101010@Z; VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)
0x18002f540  lea     rcx, ?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x18002f547  mov     rax, cs:?atStop@RunTimeInitializer@@0PEAVOnStopCallback@@EA; OnStopCallback * RunTimeInitializer::atStop
0x18002f54e  test    rax, rax
0x18002f551  jz      short loc_18002F56B
0x18002f553  mov     rdx, cs:qword_18004C130
0x18002f55a  cmp     [rax+10h], edx
0x18002f55d  jge     short loc_18002F56B
0x18002f55f  lea     rcx, [rax+8]
0x18002f563  mov     rax, [rcx]
0x18002f566  test    rax, rax
0x18002f569  jnz     short loc_18002F55A
0x18002f56b  mov     rax, [rcx]
0x18002f56e  mov     cs:qword_18004C128, rax
0x18002f575  mov     [rcx], rdi
0x18002f578  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION GlobalLockSentry::lock
0x18002f57f  add     rsp, 50h
0x18002f583  pop     rdi
0x18002f584  jmp     cs:__imp_LeaveCriticalSection
```
