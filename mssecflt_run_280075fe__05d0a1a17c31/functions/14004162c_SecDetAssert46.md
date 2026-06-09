# SecDetAssert46

- ea: `0x14004162c`
- end: `0x14004184a`
- name: `SecDetAssert46`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000ac80`

## callees

- `0x14000885c`
- `0x140009b80`
- `0x1400101a0`
- `0x140011650`
- `0x14004162c`
- `0x1400427ac`
- `0x140043cc8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140041759`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140041759`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400416ff`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400416ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004173c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041807`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004173c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041807`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400416e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140041748`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400416e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140041748`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004171e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140041778`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004171e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140041778`

## pseudocode

```c
void __fastcall SecDetAssert46(__int64 a1, char a2)
{
  wchar_t *v2; // rbp
  int ProcessCommandLine; // eax
  char v6; // bl
  unsigned int v7; // eax
  UNICODE_STRING *String1; // [rsp+40h] [rbp-28h]

  v2 = 0;
  String1 = 0;
  if ( *(_BYTE *)DetectionContext
    && _bittest64((const signed __int64 *)&xmmword_14001B740, 0x2Eu)
    && (*(_DWORD *)(a1 + 612) & 0x400) != 0
    && (*(_DWORD *)(a1 + 612) & 0x100) == 0
    && (*(_DWORD *)(a1 + 612) & 0x200) == 0 )
  {
    ProcessCommandLine = SecReadProcessCommandLine(*(HANDLE *)(a1 + 600));
    if ( ProcessCommandLine == -1073741275 )
    {
      v6 = 1;
      *(_DWORD *)(a1 + 612) |= 0x200u;
    }
    else
    {
      v6 = 0;
      if ( ProcessCommandLine < 0 )
        goto LABEL_16;
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(a1 + 560, 0);
    if ( v6 || RtlCompareUnicodeString(0, *(PCUNICODE_STRING *)(a1 + 552), 1u) )
    {
      ExReleasePushLockEx_0(a1 + 560, 0);
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1 + 560, 0);
      if ( v6 )
      {
LABEL_14:
        v7 = EventWrite46(
               (unsigned int)_InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u) + 1,
               *(_DWORD *)(a1 + 32),
               *(_QWORD *)(a1 + 40),
               *(_QWORD *)(a1 + 48),
               a2,
               *(wchar_t **)(*(_QWORD *)(a1 + 552) + 8LL),
               v2,
               v6);
        SecIncrementEtwCounters(v7);
        String1 = *(UNICODE_STRING **)(a1 + 552);
        *(_QWORD *)(a1 + 552) = 0;
        goto LABEL_15;
      }
      if ( RtlCompareUnicodeString(0, *(PCUNICODE_STRING *)(a1 + 552), 1u) )
      {
        v2 = (wchar_t *)MEMORY[8];
        goto LABEL_14;
      }
    }
LABEL_15:
    ExReleasePushLockEx_0(a1 + 560, 0);
    KeLeaveCriticalRegion();
LABEL_16:
    if ( String1 )
      SecFreePool(String1, 0x644D6353u);
  }
}

```

## disassembly

```asm
0x14004162c  mov     r11, rsp
0x14004162f  mov     [r11+18h], rbx
0x140041633  mov     [r11+20h], rbp
0x140041637  push    rsi
0x140041638  push    rdi
0x140041639  push    r14
0x14004163b  sub     rsp, 50h
0x14004163f  mov     rax, cs:__security_cookie
0x140041646  xor     rax, rsp
0x140041649  mov     [rsp+68h+var_20], rax
0x14004164e  mov     rax, cs:DetectionContext
0x140041655  xor     ebp, ebp
0x140041657  mov     qword ptr [r11-28h], 0
0x14004165f  mov     rdi, rcx
0x140041662  movzx   r14d, dl
0x140041666  mov     r8b, [rax]
0x140041669  test    r8b, r8b
0x14004166c  jz      loc_140041827
0x140041672  bt      qword ptr cs:xmmword_14001B740, 2Eh ; '.'
0x14004167b  jnb     loc_140041827
0x140041681  mov     eax, [rcx+264h]
0x140041687  bt      eax, 0Ah
0x14004168b  jnb     loc_140041827
0x140041691  mov     eax, [rcx+264h]
0x140041697  bt      eax, 8
0x14004169b  jb      loc_140041827
0x1400416a1  mov     eax, [rcx+264h]
0x1400416a7  mov     ebx, 200h
0x1400416ac  test    ebx, eax
0x1400416ae  jnz     loc_140041827
0x1400416b4  mov     rcx, [rcx+258h]; ProcessHandle
0x1400416bb  lea     rdx, [r11-28h]
0x1400416bf  call    SecReadProcessCommandLine
0x1400416c4  cmp     eax, 0C0000225h
0x1400416c9  jnz     short loc_1400416DD
0x1400416cb  mov     eax, [rdi+264h]
0x1400416d1  or      eax, ebx
0x1400416d3  mov     bl, 1
0x1400416d5  mov     [rdi+264h], eax
0x1400416db  jmp     short loc_1400416E7
0x1400416dd  xor     bl, bl
0x1400416df  test    eax, eax
0x1400416e1  js      loc_140041813
0x1400416e7  call    cs:__imp_KeEnterCriticalRegion
0x1400416ee  nop     dword ptr [rax+rax+00h]
0x1400416f3  lea     rsi, [rdi+230h]
0x1400416fa  xor     edx, edx
0x1400416fc  mov     rcx, rsi
0x1400416ff  call    cs:__imp_ExAcquirePushLockSharedEx
0x140041706  nop     dword ptr [rax+rax+00h]
0x14004170b  test    bl, bl
0x14004170d  jnz     short loc_140041732
0x14004170f  mov     rdx, [rdi+228h]; String2
0x140041716  mov     r8b, 1; CaseInSensitive
0x140041719  mov     rcx, [rsp+68h+String1]; String1
0x14004171e  call    cs:__imp_RtlCompareUnicodeString
0x140041725  nop     dword ptr [rax+rax+00h]
0x14004172a  test    eax, eax
0x14004172c  jz      loc_1400417F9
0x140041732  xor     edx, edx
0x140041734  mov     rcx, rsi
0x140041737  call    ExReleasePushLockEx_0
0x14004173c  call    cs:__imp_KeLeaveCriticalRegion
0x140041743  nop     dword ptr [rax+rax+00h]
0x140041748  call    cs:__imp_KeEnterCriticalRegion
0x14004174f  nop     dword ptr [rax+rax+00h]
0x140041754  xor     edx, edx
0x140041756  mov     rcx, rsi
0x140041759  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140041760  nop     dword ptr [rax+rax+00h]
0x140041765  test    bl, bl
0x140041767  jnz     short loc_140041791
0x140041769  mov     rdx, [rdi+228h]; String2
0x140041770  mov     r8b, 1; CaseInSensitive
0x140041773  mov     rcx, [rsp+68h+String1]; String1
0x140041778  call    cs:__imp_RtlCompareUnicodeString
0x14004177f  nop     dword ptr [rax+rax+00h]
0x140041784  test    eax, eax
0x140041786  jz      short loc_1400417F9
0x140041788  mov     rax, [rsp+68h+String1]
0x14004178d  mov     rbp, [rax+8]
0x140041791  mov     rax, [rdi+228h]
0x140041798  mov     ecx, 1
0x14004179d  mov     edx, [rdi+20h]; int
0x1400417a0  mov     r9, [rdi+30h]; int
0x1400417a4  mov     r8, [rdi+28h]; int
0x1400417a8  mov     r10, [rax+8]
0x1400417ac  mov     rax, cs:SecData
0x1400417b3  movzx   ebx, bl
0x1400417b6  lock xadd [rax+150h], rcx
0x1400417bf  mov     dword ptr [rsp+68h+var_30], ebx; char
0x1400417c3  inc     rcx; int
0x1400417c6  mov     [rsp+68h+var_38], rbp; wchar_t *
0x1400417cb  mov     [rsp+68h+Str], r10; Str
0x1400417d0  mov     dword ptr [rsp+68h+var_48], r14d; char
0x1400417d5  call    EventWrite46
0x1400417da  mov     ecx, eax
0x1400417dc  call    SecIncrementEtwCounters
0x1400417e1  mov     rcx, [rsp+68h+String1]
0x1400417e6  mov     rax, [rdi+228h]
0x1400417ed  mov     [rsp+68h+String1], rax
0x1400417f2  mov     [rdi+228h], rcx
0x1400417f9  lea     rcx, [rdi+230h]
0x140041800  xor     edx, edx
0x140041802  call    ExReleasePushLockEx_0
0x140041807  call    cs:__imp_KeLeaveCriticalRegion
0x14004180e  nop     dword ptr [rax+rax+00h]
0x140041813  mov     rcx, [rsp+68h+String1]; P
0x140041818  test    rcx, rcx
0x14004181b  jz      short loc_140041827
0x14004181d  mov     edx, 644D6353h; Tag
0x140041822  call    SecFreePool
0x140041827  mov     rcx, [rsp+68h+var_20]
0x14004182c  xor     rcx, rsp; StackCookie
0x14004182f  call    __security_check_cookie
0x140041834  lea     r11, [rsp+68h+var_18]
0x140041839  mov     rbx, [r11+30h]
0x14004183d  mov     rbp, [r11+38h]
0x140041841  mov     rsp, r11
0x140041844  pop     r14
0x140041846  pop     rdi
0x140041847  pop     rsi
0x140041848  retn
```
