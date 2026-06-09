# HacFindOpenHandles

- ea: `0x14001f9cc`
- end: `0x14001fac7`
- name: `HacFindOpenHandles`
- size: `251`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001bbbc`
- `0x14001c694`

## callees

- `0x140008140`
- `0x1400159cc`
- `0x14001f9cc`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001fa22`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001fa22`
- `ntoskrnl!KeReleaseMutex` at `0x14001fa94`
- `ntoskrnl!KeReleaseMutex` at `0x14001faa9`
- `ntoskrnl!KeReleaseMutex` at `0x14001fa94`
- `ntoskrnl!KeReleaseMutex` at `0x14001faa9`

## pseudocode

```c
char __fastcall HacFindOpenHandles(__int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rax
  const UNICODE_STRING *v4; // rbx
  const UNICODE_STRING *v5; // r12
  int Length; // ebp
  int v7; // r15d

  HacAcquireLock(a1);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v3 = *(_QWORD *)(a1 + 40);
    if ( (unsigned int)i >= *(_DWORD *)(v3 + 56) )
      break;
    v4 = *(const UNICODE_STRING **)(*(_QWORD *)(v3 + 120) + 8 * i);
    if ( v4 )
    {
      while ( v4 )
      {
        v5 = *(const UNICODE_STRING **)&v4->Length;
        Length = v4[4].Length;
        v7 = *(unsigned __int16 *)(a1 + 64);
        if ( (unsigned __int16)v7 < (unsigned __int16)Length
          && RtlCompareUnicodeString(v4 + 4, (PCUNICODE_STRING)(a1 + 64), 0) == Length - v7
          && v4[4].Buffer[(unsigned __int64)*(unsigned __int16 *)(a1 + 64) >> 1] == 92
          && (*(_DWORD *)(&v4[3].MaximumLength + 1) || LODWORD(v4[3].Buffer)) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
          }
          KeReleaseMutex(*(PRKMUTEX *)(a1 + 40), 0);
          return 1;
        }
        v4 = v5;
      }
    }
  }
  KeReleaseMutex(*(PRKMUTEX *)(a1 + 40), 0);
  return 0;
}

```

## disassembly

```asm
0x14001f9cc  push    rbx
0x14001f9ce  push    rbp
0x14001f9cf  push    rsi
0x14001f9d0  push    rdi
0x14001f9d1  push    r12
0x14001f9d3  push    r14
0x14001f9d5  push    r15
0x14001f9d7  sub     rsp, 20h
0x14001f9db  mov     rsi, rcx
0x14001f9de  call    HacAcquireLock
0x14001f9e3  xor     edi, edi
0x14001f9e5  mov     rax, [rsi+28h]
0x14001f9e9  cmp     edi, [rax+38h]
0x14001f9ec  jnb     loc_14001FAA4
0x14001f9f2  mov     rax, [rax+78h]
0x14001f9f6  mov     rbx, [rax+rdi*8]
0x14001f9fa  test    rbx, rbx
0x14001f9fd  jz      short loc_14001FA5A
0x14001f9ff  test    rbx, rbx
0x14001fa02  jz      short loc_14001FA5A
0x14001fa04  mov     r12, [rbx]
0x14001fa07  lea     rcx, [rbx+40h]; String1
0x14001fa0b  movzx   ebp, word ptr [rcx]
0x14001fa0e  lea     r14, [rsi+40h]
0x14001fa12  movzx   r15d, word ptr [r14]
0x14001fa16  cmp     r15w, bp
0x14001fa1a  jnb     short loc_14001FA55
0x14001fa1c  xor     r8d, r8d; CaseInSensitive
0x14001fa1f  mov     rdx, r14; String2
0x14001fa22  call    cs:__imp_RtlCompareUnicodeString
0x14001fa29  nop     dword ptr [rax+rax+00h]
0x14001fa2e  mov     ecx, ebp
0x14001fa30  sub     ecx, r15d
0x14001fa33  cmp     eax, ecx
0x14001fa35  jnz     short loc_14001FA55
0x14001fa37  movzx   ecx, word ptr [r14]
0x14001fa3b  mov     rax, [rbx+48h]
0x14001fa3f  shr     rcx, 1
0x14001fa42  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x14001fa47  jnz     short loc_14001FA55
0x14001fa49  cmp     dword ptr [rbx+34h], 0
0x14001fa4d  jnz     short loc_14001FA5E
0x14001fa4f  cmp     dword ptr [rbx+38h], 0
0x14001fa53  jnz     short loc_14001FA5E
0x14001fa55  mov     rbx, r12
0x14001fa58  jmp     short loc_14001F9FF
0x14001fa5a  inc     edi
0x14001fa5c  jmp     short loc_14001F9E5
0x14001fa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa65  lea     rax, WPP_GLOBAL_Control
0x14001fa6c  cmp     rcx, rax
0x14001fa6f  jz      short loc_14001FA8E
0x14001fa71  mov     edx, [rcx+2Ch]
0x14001fa74  test    dl, 2
0x14001fa77  jz      short loc_14001FA8E
0x14001fa79  mov     rcx, [rcx+18h]
0x14001fa7d  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14001fa84  mov     edx, 27h ; '''
0x14001fa89  call    WPP_SF_
0x14001fa8e  mov     rcx, [rsi+28h]; Mutex
0x14001fa92  xor     edx, edx; Wait
0x14001fa94  call    cs:__imp_KeReleaseMutex
0x14001fa9b  nop     dword ptr [rax+rax+00h]
0x14001faa0  mov     al, 1
0x14001faa2  jmp     short loc_14001FAB7
0x14001faa4  xor     edx, edx; Wait
0x14001faa6  mov     rcx, rax; Mutex
0x14001faa9  call    cs:__imp_KeReleaseMutex
0x14001fab0  nop     dword ptr [rax+rax+00h]
0x14001fab5  xor     al, al
0x14001fab7  add     rsp, 20h
0x14001fabb  pop     r15
0x14001fabd  pop     r14
0x14001fabf  pop     r12
0x14001fac1  pop     rdi
0x14001fac2  pop     rsi
0x14001fac3  pop     rbp
0x14001fac4  pop     rbx
0x14001fac5  retn
```
