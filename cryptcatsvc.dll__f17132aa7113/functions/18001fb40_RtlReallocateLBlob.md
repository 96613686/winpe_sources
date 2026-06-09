# RtlReallocateLBlob

- ea: `0x18001fb40`
- end: `0x18001fca2`
- name: `RtlReallocateLBlob`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001fa28`

## callees

- `0x18000a8b8`
- `0x18000be40`
- `0x18001fa00`
- `0x18001fb18`
- `0x18001fb40`
- `0x18001fca8`
- `0x18001fce8`

## string_xrefs

- `0x18001fc2a`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`
- `0x18001fc6b`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`

## pseudocode

```c
__int64 __fastcall RtlReallocateLBlob(__int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  __int64 v6; // r8
  __int64 StringRoutine; // rax
  int v8; // [rsp+40h] [rbp-10h] BYREF

  v8 = 0;
  if ( !a3 || !(unsigned __int8)RtlIsLBlobValid(a3) )
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(&v8);
  if ( !*(_QWORD *)(v6 + 16) )
  {
    StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine(a2);
    if ( !StringRoutine )
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(&v8);
LABEL_9:
    a3[2] = StringRoutine;
    a3[1] = a2;
    if ( *a3 > a2 )
      *a3 = a2;
    return 0;
  }
  if ( *(_QWORD *)(v6 + 8) < a2 )
  {
    StringRoutine = anonymous_namespace_::OurRtlReallocateStringRoutine(a2);
    if ( !StringRoutine )
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(&v8);
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x18001fb40  mov     [rsp-8+arg_0], rbx
0x18001fb45  mov     [rsp-8+arg_18], rdi
0x18001fb4a  push    rbp
0x18001fb4b  mov     rbp, rsp
0x18001fb4e  sub     rsp, 50h
0x18001fb52  mov     rax, cs:__security_cookie
0x18001fb59  xor     rax, rsp
0x18001fb5c  mov     [rbp+var_8], rax
0x18001fb60  mov     [rbp+var_10], 0
0x18001fb67  mov     rbx, r8
0x18001fb6a  mov     rdi, rdx
0x18001fb6d  test    r8, r8
0x18001fb70  jnz     short loc_18001FBA9
0x18001fb72  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18001fb79  mov     [rbp+var_20], 82h
0x18001fb81  mov     [rbp+var_30], rax
0x18001fb85  lea     rcx, [rbp+var_10]
0x18001fb89  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x18001fb90  mov     [rbp+var_28], rax
0x18001fb94  lea     rax, aNotNullCheckFa_7; "Not-null check failed: Blob"
0x18001fb9b  mov     [rbp+var_18], rax
0x18001fb9f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001fba4  jmp     loc_18001FC86
0x18001fba9  mov     rcx, rbx
0x18001fbac  call    RtlIsLBlobValid
0x18001fbb1  test    al, al
0x18001fbb3  jnz     short loc_18001FBEC
0x18001fbb5  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18001fbbc  mov     [rbp+var_20], 83h
0x18001fbc4  mov     [rbp+var_30], rax
0x18001fbc8  lea     rcx, [rbp+var_10]
0x18001fbcc  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x18001fbd3  mov     [rbp+var_28], rax
0x18001fbd7  lea     rax, aRtlislblobvali; "::RtlIsLBlobValid(Blob)"
0x18001fbde  mov     [rbp+var_18], rax
0x18001fbe2  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001fbe7  jmp     loc_18001FC86
0x18001fbec  mov     rdx, [r8+10h]
0x18001fbf0  test    rdx, rdx
0x18001fbf3  jz      short loc_18001FC40
0x18001fbf5  cmp     [r8+8], rdi
0x18001fbf9  jnb     loc_18001FC84
0x18001fbff  mov     rcx, rdi
0x18001fc02  call    _anonymous_namespace___OurRtlReallocateStringRoutine
0x18001fc07  test    rax, rax
0x18001fc0a  jnz     short loc_18001FC74
0x18001fc0c  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18001fc13  mov     [rbp+var_20], 94h
0x18001fc1b  mov     [rbp+var_30], rax
0x18001fc1f  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x18001fc26  mov     [rbp+var_28], rax
0x18001fc2a  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x18001fc31  lea     rcx, [rbp+var_10]
0x18001fc35  mov     [rbp+var_18], rax
0x18001fc39  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001fc3e  jmp     short loc_18001FC86
0x18001fc40  mov     rcx, rdi
0x18001fc43  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x18001fc48  test    rax, rax
0x18001fc4b  jnz     short loc_18001FC74
0x18001fc4d  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18001fc54  mov     [rbp+var_20], 99h
0x18001fc5c  mov     [rbp+var_30], rax
0x18001fc60  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x18001fc67  mov     [rbp+var_28], rax
0x18001fc6b  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x18001fc72  jmp     short loc_18001FC31
0x18001fc74  mov     [rbx+10h], rax
0x18001fc78  mov     [rbx+8], rdi
0x18001fc7c  cmp     [rbx], rdi
0x18001fc7f  jbe     short loc_18001FC84
0x18001fc81  mov     [rbx], rdi
0x18001fc84  xor     eax, eax
0x18001fc86  mov     rcx, [rbp+var_8]
0x18001fc8a  xor     rcx, rsp; StackCookie
0x18001fc8d  call    __security_check_cookie
0x18001fc92  mov     rbx, [rsp+50h+arg_0]
0x18001fc97  mov     rdi, [rsp+50h+arg_18]
0x18001fc9c  add     rsp, 50h
0x18001fca0  pop     rbp
0x18001fca1  retn
```
