# IASSamLookupUser

- ea: `0x18002aa10`
- end: `0x18002aacd`
- name: `IASSamLookupUser`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002addc`

## callees

- `0x18002aa10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002aa44`
- `ntdll!RtlInitUnicodeString` at `0x18002aa44`
- `ntdll!RtlNtStatusToDosError` at `0x18002aab7`
- `ntdll!RtlNtStatusToDosError` at `0x18002aab7`
- `SAMLIB!SamLookupNamesInDomain` at `0x18002aa69`
- `SAMLIB!SamLookupNamesInDomain` at `0x18002aa69`
- `SAMLIB!SamOpenUser` at `0x18002aaaf`
- `SAMLIB!SamOpenUser` at `0x18002aaaf`
- `SAMLIB!SamFreeMemory` at `0x18002aa7d`
- `SAMLIB!SamFreeMemory` at `0x18002aa88`
- `SAMLIB!SamFreeMemory` at `0x18002aa7d`
- `SAMLIB!SamFreeMemory` at `0x18002aa88`

## pseudocode

```c
ULONG __fastcall IASSamLookupUser(__int64 a1, const WCHAR *a2, unsigned int a3, unsigned int *a4, __int64 a5)
{
  NTSTATUS v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING v12[4]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int *v13; // [rsp+88h] [rbp+10h] BYREF

  v13 = 0;
  v11 = 0;
  v12[0] = 0;
  if ( a2 )
  {
    RtlInitUnicodeString(v12, a2);
    v8 = SamLookupNamesInDomain(a1, 1, v12, &v13, &v11);
    if ( v8 < 0 )
      return RtlNtStatusToDosError(v8);
    v9 = *v13;
    SamFreeMemory(v13);
    SamFreeMemory(v11);
    if ( a4 )
      *a4 = v9;
LABEL_7:
    v8 = SamOpenUser(a1, a3, v9, a5);
    return RtlNtStatusToDosError(v8);
  }
  if ( a4 )
  {
    v9 = *a4;
    goto LABEL_7;
  }
  return 87;
}

```

## disassembly

```asm
0x18002aa10  mov     rax, rsp
0x18002aa13  push    rbx
0x18002aa14  push    rbp
0x18002aa15  push    rsi
0x18002aa16  push    rdi
0x18002aa17  sub     rsp, 58h
0x18002aa1b  mov     qword ptr [rax+10h], 0
0x18002aa23  xorps   xmm0, xmm0
0x18002aa26  mov     qword ptr [rax-48h], 0
0x18002aa2e  mov     rbx, r9
0x18002aa31  mov     ebp, r8d
0x18002aa34  mov     rsi, rcx
0x18002aa37  movups  xmmword ptr [rax-40h], xmm0
0x18002aa3b  test    rdx, rdx
0x18002aa3e  jz      short loc_18002AA97
0x18002aa40  lea     rcx, [rax-40h]; DestinationString
0x18002aa44  call    cs:__imp_RtlInitUnicodeString
0x18002aa4a  lea     rax, [rsp+78h+var_48]
0x18002aa4f  mov     edx, 1
0x18002aa54  lea     r9, [rsp+78h+arg_8]
0x18002aa5c  mov     [rsp+78h+var_58], rax
0x18002aa61  lea     r8, [rsp+78h+var_40]
0x18002aa66  mov     rcx, rsi
0x18002aa69  call    cs:__imp_SamLookupNamesInDomain
0x18002aa6f  test    eax, eax
0x18002aa71  js      short loc_18002AAB5
0x18002aa73  mov     rcx, [rsp+78h+arg_8]
0x18002aa7b  mov     edi, [rcx]
0x18002aa7d  call    cs:__imp_SamFreeMemory
0x18002aa83  mov     rcx, [rsp+78h+var_48]
0x18002aa88  call    cs:__imp_SamFreeMemory
0x18002aa8e  test    rbx, rbx
0x18002aa91  jz      short loc_18002AA9F
0x18002aa93  mov     [rbx], edi
0x18002aa95  jmp     short loc_18002AA9F
0x18002aa97  test    rbx, rbx
0x18002aa9a  jz      short loc_18002AABF
0x18002aa9c  mov     edi, [r9]
0x18002aa9f  mov     r9, [rsp+78h+arg_20]
0x18002aaa7  mov     r8d, edi
0x18002aaaa  mov     edx, ebp
0x18002aaac  mov     rcx, rsi
0x18002aaaf  call    cs:__imp_SamOpenUser
0x18002aab5  mov     ecx, eax; Status
0x18002aab7  call    cs:__imp_RtlNtStatusToDosError
0x18002aabd  jmp     short loc_18002AAC4
0x18002aabf  mov     eax, 57h ; 'W'
0x18002aac4  add     rsp, 58h
0x18002aac8  pop     rdi
0x18002aac9  pop     rsi
0x18002aaca  pop     rbp
0x18002aacb  pop     rbx
0x18002aacc  retn
```
