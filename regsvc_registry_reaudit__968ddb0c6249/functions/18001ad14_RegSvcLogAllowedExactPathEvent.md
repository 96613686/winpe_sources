# RegSvcLogAllowedExactPathEvent

- ea: `0x18001ad14`
- end: `0x18001ae35`
- name: `RegSvcLogAllowedExactPathEvent`
- size: `289`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019290`
- `0x1800199a0`

## callees

- `0x180007740`
- `0x180016c10`
- `0x18001ad14`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001ad70`
- `ntdll!RtlNtStatusToDosError` at `0x18001adce`
- `ntdll!RtlNtStatusToDosError` at `0x18001ad70`
- `ntdll!RtlNtStatusToDosError` at `0x18001adce`
- `ntdll!RtlInitUnicodeString` at `0x18001adeb`
- `ntdll!RtlInitUnicodeString` at `0x18001adeb`
- `ntdll!RtlFreeHeap` at `0x18001ae10`
- `ntdll!RtlFreeHeap` at `0x18001ae10`
- `ntdll!NtQueryKey` at `0x18001ad68`
- `ntdll!NtQueryKey` at `0x18001adc6`
- `ntdll!NtQueryKey` at `0x18001ad68`
- `ntdll!NtQueryKey` at `0x18001adc6`
- `ntdll!RtlAllocateHeap` at `0x18001ad9e`
- `ntdll!RtlAllocateHeap` at `0x18001ad9e`

## pseudocode

```c
char __fastcall RegSvcLogAllowedExactPathEvent(HANDLE KeyHandle, unsigned __int16 *a2)
{
  NTSTATUS v4; // eax
  WCHAR *Heap; // rax
  WCHAR *v6; // rbx
  NTSTATUS v7; // eax
  __int64 v8; // rcx
  ULONG Length; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+48h] [rbp-20h] BYREF

  Length = 0;
  v12 = 0;
  DestinationString = 0;
  v4 = NtQueryKey(KeyHandle, KeyNameInformation, &v12, 8u, &Length);
  LODWORD(Heap) = RtlNtStatusToDosError(v4);
  if ( (_DWORD)Heap == 234 )
  {
    Length += 2;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
    v6 = Heap;
    if ( Heap )
    {
      v7 = NtQueryKey(KeyHandle, KeyNameInformation, Heap, Length, &Length);
      if ( !RtlNtStatusToDosError(v7) )
      {
        v6[((unsigned __int64)*(unsigned int *)v6 >> 1) + 2] = 0;
        RtlInitUnicodeString(&DestinationString, v6 + 2);
        RegSvcLogEvent(v8, a2, &DestinationString.Length);
      }
      LOBYTE(Heap) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    }
  }
  return (char)Heap;
}

```

## disassembly

```asm
0x18001ad14  mov     r11, rsp
0x18001ad17  mov     [r11+18h], rbx
0x18001ad1b  mov     [r11+20h], rsi
0x18001ad1f  push    rdi
0x18001ad20  sub     rsp, 60h
0x18001ad24  mov     rax, cs:__security_cookie
0x18001ad2b  xor     rax, rsp
0x18001ad2e  mov     [rsp+68h+var_18], rax
0x18001ad33  mov     ebx, 8
0x18001ad38  mov     [rsp+68h+Length], 0
0x18001ad40  mov     rsi, rdx
0x18001ad43  mov     qword ptr [r11-20h], 0
0x18001ad4b  xorps   xmm0, xmm0
0x18001ad4e  lea     rax, [r11-38h]
0x18001ad52  mov     r9d, ebx; Length
0x18001ad55  mov     [r11-48h], rax
0x18001ad59  lea     edx, [rbx-5]; KeyInformationClass
0x18001ad5c  mov     rdi, rcx
0x18001ad5f  lea     r8, [r11-20h]; KeyInformation
0x18001ad63  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18001ad68  call    cs:__imp_NtQueryKey
0x18001ad6e  mov     ecx, eax; Status
0x18001ad70  call    cs:__imp_RtlNtStatusToDosError
0x18001ad76  cmp     eax, 0EAh
0x18001ad7b  jnz     loc_18001AE16
0x18001ad81  mov     eax, [rsp+68h+Length]
0x18001ad85  mov     edx, ebx; Flags
0x18001ad87  add     eax, 2
0x18001ad8a  mov     [rsp+68h+Length], eax
0x18001ad8e  mov     rcx, gs:60h
0x18001ad97  mov     r8d, eax; Size
0x18001ad9a  mov     rcx, [rcx+30h]; HeapHandle
0x18001ad9e  call    cs:__imp_RtlAllocateHeap
0x18001ada4  mov     rbx, rax
0x18001ada7  test    rax, rax
0x18001adaa  jz      short loc_18001AE16
0x18001adac  mov     r9d, [rsp+68h+Length]; Length
0x18001adb1  lea     rax, [rsp+68h+Length]
0x18001adb6  mov     r8, rbx; KeyInformation
0x18001adb9  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18001adbe  mov     edx, 3; KeyInformationClass
0x18001adc3  mov     rcx, rdi; KeyHandle
0x18001adc6  call    cs:__imp_NtQueryKey
0x18001adcc  mov     ecx, eax; Status
0x18001adce  call    cs:__imp_RtlNtStatusToDosError
0x18001add4  test    eax, eax
0x18001add6  jnz     short loc_18001ADFE
0x18001add8  mov     ecx, [rbx]
0x18001adda  lea     rdx, [rbx+4]; SourceString
0x18001adde  shr     rcx, 1
0x18001ade1  mov     [rbx+rcx*2+4], ax
0x18001ade6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18001adeb  call    cs:__imp_RtlInitUnicodeString
0x18001adf1  lea     r8, [rsp+68h+DestinationString]
0x18001adf6  mov     rdx, rsi
0x18001adf9  call    RegSvcLogEvent
0x18001adfe  mov     rcx, gs:60h
0x18001ae07  mov     r8, rbx; P
0x18001ae0a  xor     edx, edx; Flags
0x18001ae0c  mov     rcx, [rcx+30h]; HeapHandle
0x18001ae10  call    cs:__imp_RtlFreeHeap
0x18001ae16  mov     rcx, [rsp+68h+var_18]
0x18001ae1b  xor     rcx, rsp; StackCookie
0x18001ae1e  call    __security_check_cookie
0x18001ae23  lea     r11, [rsp+68h+var_8]
0x18001ae28  mov     rbx, [r11+20h]
0x18001ae2c  mov     rsi, [r11+28h]
0x18001ae30  mov     rsp, r11
0x18001ae33  pop     rdi
0x18001ae34  retn
```
