# MRxDAVCancelTheContext

- ea: `0x140004350`
- end: `0x1400044a7`
- name: `MRxDAVCancelTheContext`
- size: `343`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400041c0`
- `0x140005554`

## callees

- `0x140001680`
- `0x1400017e4`
- `0x140004350`
- `0x1400044b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000438a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004414`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000446e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000438a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004414`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000446e`

## pseudocode

```c
__int64 __fastcall MRxDAVCancelTheContext(__int64 a1, unsigned int a2, int a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rbx
  HANDLE CurrentThreadId; // rax
  unsigned int v9; // edi
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rdx

  v6 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qq(v7, 19, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId, a1);
  }
  v9 = *(_DWORD *)(a1 + 744);
  if ( v9 == 9 || *(_DWORD *)(a1 + 744) == 10 )
    return v6;
  if ( a2 && (v9 <= 4 || v9 - 5 <= 1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      v12 = 20;
LABEL_12:
      WPP_SF_qD(v10, v12, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v11, v9);
      return v6;
    }
    return v6;
  }
  v9 = *(_DWORD *)(a1 + 48);
  if ( v9 < 2 )
  {
    *(_DWORD *)(a1 + 48) = 3;
    return (unsigned int)MRxDAVCompleteTheCancelledRequest(a1, a2);
  }
  if ( v9 == 3 && a3 )
    return (unsigned int)MRxDAVCompleteTheCancelledRequest(a1, a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v11 = PsGetCurrentThreadId();
    v12 = 21;
    goto LABEL_12;
  }
  return v6;
}

```

## disassembly

```asm
0x140004350  push    rbx
0x140004352  push    rbp
0x140004353  push    rsi
0x140004354  push    rdi
0x140004355  push    r12
0x140004357  push    r14
0x140004359  push    r15
0x14000435b  sub     rsp, 30h
0x14000435f  mov     r15d, r8d
0x140004362  mov     r14d, edx
0x140004365  mov     rsi, rcx
0x140004368  xor     ebp, ebp
0x14000436a  mov     rbx, cs:WPP_GLOBAL_Control
0x140004371  lea     r12, WPP_GLOBAL_Control
0x140004378  cmp     rbx, r12
0x14000437b  jz      short loc_1400043B0
0x14000437d  test    dword ptr [rbx+2Ch], 4000h
0x140004384  jz      short loc_1400043B0
0x140004386  mov     rbx, [rbx+18h]
0x14000438a  call    cs:__imp_PsGetCurrentThreadId
0x140004391  nop     dword ptr [rax+rax+00h]
0x140004396  lea     edx, [rbp+13h]
0x140004399  mov     [rsp+68h+var_48], rsi
0x14000439e  mov     r9, rax
0x1400043a1  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x1400043a8  mov     rcx, rbx
0x1400043ab  call    WPP_SF_qq
0x1400043b0  mov     edi, [rsi+2E8h]
0x1400043b6  mov     ecx, edi
0x1400043b8  sub     ecx, 9
0x1400043bb  jz      loc_140004495
0x1400043c1  cmp     ecx, 1
0x1400043c4  jz      loc_140004495
0x1400043ca  test    r14d, r14d
0x1400043cd  jz      short loc_14000443D
0x1400043cf  mov     ecx, edi
0x1400043d1  test    edi, edi
0x1400043d3  jz      short loc_1400043F3
0x1400043d5  sub     ecx, 1
0x1400043d8  jz      short loc_1400043F3
0x1400043da  sub     ecx, 1
0x1400043dd  jz      short loc_1400043F3
0x1400043df  sub     ecx, 1
0x1400043e2  jz      short loc_1400043F3
0x1400043e4  sub     ecx, 1
0x1400043e7  jz      short loc_1400043F3
0x1400043e9  sub     ecx, 1
0x1400043ec  jz      short loc_1400043F3
0x1400043ee  cmp     ecx, 1
0x1400043f1  jnz     short loc_14000443D
0x1400043f3  mov     rbx, cs:WPP_GLOBAL_Control
0x1400043fa  cmp     rbx, r12
0x1400043fd  jz      loc_140004495
0x140004403  test    dword ptr [rbx+2Ch], 2000h
0x14000440a  jz      loc_140004495
0x140004410  mov     rbx, [rbx+18h]
0x140004414  call    cs:__imp_PsGetCurrentThreadId
0x14000441b  nop     dword ptr [rax+rax+00h]
0x140004420  mov     edx, 14h
0x140004425  mov     r9, rax
0x140004428  mov     dword ptr [rsp+68h+var_48], edi
0x14000442c  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140004433  mov     rcx, rbx
0x140004436  call    WPP_SF_qD
0x14000443b  jmp     short loc_140004495
0x14000443d  mov     edi, [rsi+30h]
0x140004440  mov     ecx, edi
0x140004442  test    edi, edi
0x140004444  jz      short loc_140004481
0x140004446  sub     ecx, 1
0x140004449  jz      short loc_140004481
0x14000444b  cmp     ecx, 2
0x14000444e  jnz     short loc_140004455
0x140004450  test    r15d, r15d
0x140004453  jnz     short loc_140004488
0x140004455  mov     rbx, cs:WPP_GLOBAL_Control
0x14000445c  cmp     rbx, r12
0x14000445f  jz      short loc_140004495
0x140004461  test    dword ptr [rbx+2Ch], 4000h
0x140004468  jz      short loc_140004495
0x14000446a  mov     rbx, [rbx+18h]
0x14000446e  call    cs:__imp_PsGetCurrentThreadId
0x140004475  nop     dword ptr [rax+rax+00h]
0x14000447a  mov     edx, 15h
0x14000447f  jmp     short loc_140004425
0x140004481  mov     dword ptr [rsi+30h], 3
0x140004488  mov     edx, r14d
0x14000448b  mov     rcx, rsi
0x14000448e  call    MRxDAVCompleteTheCancelledRequest
0x140004493  mov     ebp, eax
0x140004495  mov     eax, ebp
0x140004497  add     rsp, 30h
0x14000449b  pop     r15
0x14000449d  pop     r14
0x14000449f  pop     r12
0x1400044a1  pop     rdi
0x1400044a2  pop     rsi
0x1400044a3  pop     rbp
0x1400044a4  pop     rbx
0x1400044a5  retn
```
