# WerEscalationLazyInit

- ea: `0x1800ccde8`
- end: `0x1800cd1c0`
- name: `WerEscalationLazyInit`
- size: `984`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ccab0`
- `0x1800ccb00`

## callees

- `0x180014e60`
- `0x180015710`
- `0x18005a9f0`
- `0x1800ccde8`
- `0x1800cd540`
- `0x1800cda3c`
- `0x18011f07c`
- `0x180139eac`
- `0x18015e4b0`
- `0x18015e5d0`
- `0x18015e690`
- `0x18015e6f0`
- `0x180160920`

## string_xrefs

- `0x1800cd057`: `\REGISTRY\USER\`

## pseudocode

```c
__int64 WerEscalationLazyInit()
{
  __int64 v0; // rax
  NTSTATUS appended; // ebx
  signed __int64 v2; // rdi
  char *v3; // r14
  _WORD *v4; // rsi
  __int64 v5; // rdx
  _WORD *v6; // rax
  unsigned int v7; // r11d
  wchar_t *Buffer; // r9
  __int64 v9; // rcx
  wchar_t *v10; // r8
  _WORD *v11; // rcx
  wchar_t *i; // rcx
  char *v13; // r15
  unsigned __int16 v14; // bx
  _WORD *v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned int v21; // eax
  _WORD *v22; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-30h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-28h] BYREF
  __int128 v25; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v26; // [rsp+B0h] [rbp+48h] BYREF
  int v27; // [rsp+B8h] [rbp+50h] BYREF
  int v28; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+60h] BYREF

  v0 = g_werEscalationData;
  Handle = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v22 = 0;
  v28 = 0;
  UnicodeString = 0;
  v25 = 0;
  if ( g_werEscalationData && g_sqmSessionHandle != -1 )
    return 0;
  appended = -1073741823;
  v2 = 0;
  if ( !g_disableEscalation )
  {
    g_disableEscalation = WerpEscalationIsDisabled();
    v0 = g_werEscalationData;
  }
  if ( v0 )
    goto LABEL_24;
  v29 = 568;
  v22 = 0;
  appended = ZwAllocateVirtualMemory(-1, &v22, 0, &v29, 4096, 4);
  if ( appended >= 0 )
  {
    v2 = (signed __int64)v22;
    v3 = (char *)v22 + v29;
    v4 = v22 + 284;
    if ( v22 + 284 > (_WORD *)((char *)v22 + v29) )
      goto LABEL_33;
    v5 = 260;
    v6 = v22;
    v7 = NtCurrentPeb()->ProcessParameters->ImagePathName.Length >> 1;
    Buffer = NtCurrentPeb()->ProcessParameters->ImagePathName.Buffer;
    v9 = 2147483646;
    v10 = Buffer;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v6++ = *v10++;
      --v9;
      --v5;
    }
    while ( v5 );
    v11 = v6 - 1;
    if ( v5 )
      v11 = v6;
    *v11 = 0;
    for ( i = &Buffer[v7 - 1]; i > Buffer; --i )
    {
      if ( *i == 92 || *i == 47 )
      {
        ++i;
        break;
      }
    }
    *(_DWORD *)(v2 + 520) = HashStringToDwordCaseInsensitiveLen(i, v7 - (unsigned int)(i - Buffer), v10);
    WerEscalationReadImageVersionInfoForModuleBaseSafe(NtCurrentPeb()->ImageBaseAddress, 0, &v25);
    *(_DWORD *)(v2 + 532) = v25;
    *(_QWORD *)(v2 + 524) = *((_QWORD *)&v25 + 1);
    appended = NtOpenProcessToken(-1, 8, &Handle);
    if ( appended < 0 )
      goto LABEL_26;
    v26 = (_DWORD)v3 - (_DWORD)v4;
    appended = NtQueryInformationToken(Handle, 1, v4, (unsigned int)((_DWORD)v3 - (_DWORD)v4), &v26);
    if ( appended < 0 )
      goto LABEL_26;
    v13 = (char *)&v4[4 * (((unsigned __int64)v26 + 7) >> 3)];
    if ( v13 > v3 )
      goto LABEL_33;
    *(_QWORD *)(v2 + 536) = *(_QWORD *)v4;
    *(_DWORD *)(v2 + 560) = 0x40000000;
    if ( (int)NtQueryInformationToken(Handle, 18, &v27, 4, &v26) >= 0 )
    {
      if ( v27 == 2 )
      {
        *(_DWORD *)(v2 + 560) = -1073741824;
      }
      else if ( v27 == 1 )
      {
        v21 = 0;
        if ( *(_DWORD *)(*(_QWORD *)v4 + 4LL * ((unsigned int)*(unsigned __int8 *)(*(_QWORD *)v4 + 1LL) - 1) + 8) == 500 )
          v21 = 0x80000000;
        *(_DWORD *)(v2 + 560) = v21;
      }
    }
    appended = RtlLengthSidAsUnicodeString(*(_QWORD *)(v2 + 536), &v28);
    if ( appended < 0 )
      goto LABEL_26;
    v14 = v28;
    v15 = (_WORD *)(v2 + 544);
    *(_WORD *)(v2 + 544) = 0;
    *(_QWORD *)(v2 + 552) = v13;
    v16 = (unsigned __int16)(v14 + 90);
    *(_WORD *)(v2 + 546) = v16;
    if ( &v13[v16] > v3 )
    {
LABEL_33:
      appended = -1073741789;
    }
    else
    {
      RtlAppendUnicodeToString(v2 + 544, L"\\REGISTRY\\USER\\");
      v17 = *(_QWORD *)(v2 + 552);
      v18 = *(void **)(v2 + 536);
      v19 = (unsigned __int64)(unsigned __int16)*v15 >> 1;
      UnicodeString.MaximumLength = v14;
      UnicodeString.Length = 0;
      UnicodeString.Buffer = (wchar_t *)(v17 + 2 * v19);
      appended = RtlConvertSidToUnicodeString(&UnicodeString, v18, 0);
      if ( appended >= 0 )
      {
        *v15 += UnicodeString.Length;
        appended = RtlAppendUnicodeToString(v2 + 544, L"\\Software\\Microsoft\\Windows");
        if ( appended >= 0 )
        {
          *(_DWORD *)(v2 + 564) = WerpEscalationIsWMRSendStringSet();
          v2 &= -(__int64)(_InterlockedCompareExchange64(&g_werEscalationData, v2, 0) != 0);
LABEL_24:
          if ( g_sqmSessionHandle != -1 )
            appended = 0;
        }
      }
    }
LABEL_26:
    if ( v2 )
      ZwFreeVirtualMemory(-1, &v22, &v29, 0x8000);
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800ccde8  push    rbp
0x1800ccdea  push    rbx
0x1800ccdeb  push    rsi
0x1800ccdec  push    rdi
0x1800ccded  push    r12
0x1800ccdef  push    r13
0x1800ccdf1  push    r14
0x1800ccdf3  push    r15
0x1800ccdf5  mov     rbp, rsp
0x1800ccdf8  sub     rsp, 68h
0x1800ccdfc  mov     rax, cs:g_werEscalationData
0x1800cce03  xor     r12d, r12d
0x1800cce06  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800cce0a  mov     [rbp+Handle], r12
0x1800cce0e  mov     [rbp+arg_0], r12d
0x1800cce12  xorps   xmm0, xmm0
0x1800cce15  mov     [rbp+arg_8], r12d
0x1800cce19  xorps   xmm1, xmm1
0x1800cce1c  mov     [rbp+arg_18], r12
0x1800cce20  mov     [rbp+var_38], r12
0x1800cce24  mov     [rbp+arg_10], r12d
0x1800cce28  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800cce2c  movups  [rbp+var_18], xmm1
0x1800cce30  test    rax, rax
0x1800cce33  jnz     loc_1800CD110
0x1800cce39  cmp     cs:g_disableEscalation, r12d
0x1800cce40  mov     ebx, 0C0000001h
0x1800cce45  mov     rdi, r12
0x1800cce48  jz      loc_1800CD121
0x1800cce4e  test    rax, rax
0x1800cce51  jnz     loc_1800CD0D8
0x1800cce57  mov     [rsp+68h+var_40], 4
0x1800cce5f  lea     r9, [rbp+arg_18]
0x1800cce63  xor     r8d, r8d
0x1800cce66  mov     dword ptr [rsp+68h+var_48], 1000h
0x1800cce6e  lea     rdx, [rbp+var_38]
0x1800cce72  mov     [rbp+arg_18], 238h
0x1800cce7a  mov     rcx, r13
0x1800cce7d  mov     [rbp+var_38], r12
0x1800cce81  call    ZwAllocateVirtualMemory
0x1800cce86  mov     ebx, eax
0x1800cce88  test    eax, eax
0x1800cce8a  js      loc_1800CD0EC
0x1800cce90  mov     rdi, [rbp+var_38]
0x1800cce94  mov     r14, [rbp+arg_18]
0x1800cce98  add     r14, rdi
0x1800cce9b  lea     rsi, [rdi+238h]
0x1800ccea2  cmp     rsi, r14
0x1800ccea5  ja      loc_1800CD138
0x1800cceab  mov     rax, gs:60h
0x1800cceb4  mov     edx, 104h
0x1800cceb9  mov     rcx, [rax+20h]
0x1800ccebd  mov     rax, gs:60h
0x1800ccec6  movzx   r11d, word ptr [rcx+60h]
0x1800ccecb  mov     rcx, [rax+20h]
0x1800ccecf  mov     rax, rdi
0x1800cced2  shr     r11d, 1
0x1800cced5  mov     r9, [rcx+68h]
0x1800cced9  mov     ecx, 7FFFFFFEh
0x1800ccede  mov     r8, r9
0x1800ccee1  test    rcx, rcx
0x1800ccee4  jz      short loc_1800CCF05
0x1800ccee6  movzx   r10d, word ptr [r8]
0x1800cceea  test    r10w, r10w
0x1800cceee  jz      short loc_1800CCF05
0x1800ccef0  mov     [rax], r10w
0x1800ccef4  add     r8, 2
0x1800ccef8  add     rax, 2
0x1800ccefc  dec     rcx
0x1800cceff  sub     rdx, 1
0x1800ccf03  jnz     short loc_1800CCEE1
0x1800ccf05  test    rdx, rdx
0x1800ccf08  lea     rcx, [rax-2]
0x1800ccf0c  cmovnz  rcx, rax
0x1800ccf10  mov     [rcx], r12w
0x1800ccf14  lea     rcx, [r9-2]
0x1800ccf18  lea     rcx, [rcx+r11*2]
0x1800ccf1c  cmp     rcx, r9
0x1800ccf1f  ja      loc_1800CD13F
0x1800ccf25  mov     rax, rcx
0x1800ccf28  sub     rax, r9
0x1800ccf2b  sar     rax, 1
0x1800ccf2e  sub     r11d, eax
0x1800ccf31  mov     edx, r11d
0x1800ccf34  call    HashStringToDwordCaseInsensitiveLen
0x1800ccf39  mov     [rdi+208h], eax
0x1800ccf3f  lea     r8, [rbp+var_18]
0x1800ccf43  mov     rcx, gs:60h
0x1800ccf4c  xor     edx, edx
0x1800ccf4e  mov     rcx, [rcx+10h]
0x1800ccf52  call    WerEscalationReadImageVersionInfoForModuleBaseSafe
0x1800ccf57  mov     eax, dword ptr [rbp+var_18]
0x1800ccf5a  lea     r8, [rbp+Handle]
0x1800ccf5e  mov     [rdi+214h], eax
0x1800ccf64  mov     edx, 8
0x1800ccf69  mov     eax, dword ptr [rbp+var_18+8]
0x1800ccf6c  mov     rcx, r13
0x1800ccf6f  mov     [rdi+20Ch], eax
0x1800ccf75  mov     eax, dword ptr [rbp+var_18+0Ch]
0x1800ccf78  mov     [rdi+210h], eax
0x1800ccf7e  call    NtOpenProcessToken
0x1800ccf83  mov     ebx, eax
0x1800ccf85  test    eax, eax
0x1800ccf87  js      loc_1800CD0E3
0x1800ccf8d  mov     rcx, [rbp+Handle]
0x1800ccf91  lea     rax, [rbp+arg_0]
0x1800ccf95  mov     r9d, r14d
0x1800ccf98  mov     [rsp+68h+var_48], rax
0x1800ccf9d  sub     r9d, esi
0x1800ccfa0  mov     r8, rsi
0x1800ccfa3  mov     edx, 1
0x1800ccfa8  mov     [rbp+arg_0], r9d
0x1800ccfac  call    NtQueryInformationToken
0x1800ccfb1  mov     ebx, eax
0x1800ccfb3  test    eax, eax
0x1800ccfb5  js      loc_1800CD0E3
0x1800ccfbb  mov     eax, [rbp+arg_0]
0x1800ccfbe  add     rax, 7
0x1800ccfc2  shr     rax, 3
0x1800ccfc6  lea     r15, [rsi+rax*8]
0x1800ccfca  cmp     r15, r14
0x1800ccfcd  ja      loc_1800CD138
0x1800ccfd3  mov     rax, [rsi]
0x1800ccfd6  lea     r8, [rbp+arg_8]
0x1800ccfda  mov     [rdi+218h], rax
0x1800ccfe1  mov     r9d, 4
0x1800ccfe7  mov     dword ptr [rdi+230h], 40000000h
0x1800ccff1  lea     rax, [rbp+arg_0]
0x1800ccff5  mov     rcx, [rbp+Handle]
0x1800ccff9  mov     [rsp+68h+var_48], rax
0x1800ccffe  lea     edx, [r9+0Eh]
0x1800cd002  call    NtQueryInformationToken
0x1800cd007  test    eax, eax
0x1800cd009  jns     loc_1800CD15D
0x1800cd00f  mov     rcx, [rdi+218h]
0x1800cd016  lea     rdx, [rbp+arg_10]
0x1800cd01a  call    RtlLengthSidAsUnicodeString
0x1800cd01f  mov     ebx, eax
0x1800cd021  test    eax, eax
0x1800cd023  js      loc_1800CD0E3
0x1800cd029  mov     ebx, [rbp+arg_10]
0x1800cd02c  lea     rsi, [rdi+220h]
0x1800cd033  mov     [rsi], r12w
0x1800cd037  mov     [rdi+228h], r15
0x1800cd03e  lea     eax, [rbx+5Ah]
0x1800cd041  movzx   ecx, ax
0x1800cd044  mov     [rdi+222h], cx
0x1800cd04b  add     rcx, r15
0x1800cd04e  cmp     rcx, r14
0x1800cd051  ja      loc_1800CD138
0x1800cd057  lea     rdx, aRegistryUser; "\\REGISTRY\\USER\\"
0x1800cd05e  mov     rcx, rsi
0x1800cd061  call    RtlAppendUnicodeToString
0x1800cd066  movzx   ecx, word ptr [rsi]
0x1800cd069  xor     r8d, r8d; AllocateDestinationString
0x1800cd06c  mov     rax, [rdi+228h]
0x1800cd073  mov     rdx, [rdi+218h]; Sid
0x1800cd07a  shr     rcx, 1
0x1800cd07d  mov     [rbp+UnicodeString.MaximumLength], bx
0x1800cd081  mov     [rbp+UnicodeString.Length], r12w
0x1800cd086  lea     rcx, [rax+rcx*2]
0x1800cd08a  mov     [rbp+UnicodeString.Buffer], rcx
0x1800cd08e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800cd092  call    RtlConvertSidToUnicodeString
0x1800cd097  mov     ebx, eax
0x1800cd099  test    eax, eax
0x1800cd09b  js      short loc_1800CD0E3
0x1800cd09d  movzx   eax, [rbp+UnicodeString.Length]
0x1800cd0a1  lea     rdx, aSoftwareMicros_1; "\\Software\\Microsoft\\Windows"
0x1800cd0a8  add     [rsi], ax
0x1800cd0ab  mov     rcx, rsi
0x1800cd0ae  call    RtlAppendUnicodeToString
0x1800cd0b3  mov     ebx, eax
0x1800cd0b5  test    eax, eax
0x1800cd0b7  js      short loc_1800CD0E3
0x1800cd0b9  call    WerpEscalationIsWMRSendStringSet
0x1800cd0be  mov     [rdi+234h], eax
0x1800cd0c4  xor     eax, eax
0x1800cd0c6  lock cmpxchg cs:g_werEscalationData, rdi
0x1800cd0cf  neg     rax
0x1800cd0d2  sbb     rcx, rcx
0x1800cd0d5  and     rdi, rcx
0x1800cd0d8  cmp     cs:g_sqmSessionHandle, r13
0x1800cd0df  cmovnz  ebx, r12d
0x1800cd0e3  test    rdi, rdi
0x1800cd0e6  jnz     loc_1800CD1A5
0x1800cd0ec  mov     rcx, [rbp+Handle]; Handle
0x1800cd0f0  test    rcx, rcx
0x1800cd0f3  jnz     short loc_1800CD109
0x1800cd0f5  mov     eax, ebx
0x1800cd0f7  add     rsp, 68h
0x1800cd0fb  pop     r15
0x1800cd0fd  pop     r14
0x1800cd0ff  pop     r13
0x1800cd101  pop     r12
0x1800cd103  pop     rdi
0x1800cd104  pop     rsi
0x1800cd105  pop     rbx
0x1800cd106  pop     rbp
0x1800cd107  retn
0x1800cd109  call    NtClose
0x1800cd10e  jmp     short loc_1800CD0F5
0x1800cd110  cmp     cs:g_sqmSessionHandle, r13
0x1800cd117  jz      loc_1800CCE39
0x1800cd11d  xor     eax, eax
0x1800cd11f  jmp     short loc_1800CD0F7
0x1800cd121  call    WerpEscalationIsDisabled
0x1800cd126  mov     cs:g_disableEscalation, eax
0x1800cd12c  mov     rax, cs:g_werEscalationData
0x1800cd133  jmp     loc_1800CCE4E
0x1800cd138  mov     ebx, 0C0000023h
0x1800cd13d  jmp     short loc_1800CD0E3
0x1800cd13f  cmp     word ptr [rcx], 5Ch ; '\'
0x1800cd143  jz      short loc_1800CD154
0x1800cd145  cmp     word ptr [rcx], 2Fh ; '/'
0x1800cd149  jz      short loc_1800CD154
0x1800cd14b  sub     rcx, 2
0x1800cd14f  jmp     loc_1800CCF1C
0x1800cd154  add     rcx, 2
0x1800cd158  jmp     loc_1800CCF25
0x1800cd15d  cmp     [rbp+arg_8], 2
0x1800cd161  jnz     short loc_1800CD172
0x1800cd163  mov     dword ptr [rdi+230h], 0C0000000h
0x1800cd16d  jmp     loc_1800CD00F
0x1800cd172  cmp     [rbp+arg_8], 1
0x1800cd176  jnz     loc_1800CD00F
0x1800cd17c  mov     rdx, [rsi]
0x1800cd17f  mov     eax, r12d
0x1800cd182  mov     r8d, 80000000h
0x1800cd188  movzx   ecx, byte ptr [rdx+1]
0x1800cd18c  dec     ecx
0x1800cd18e  cmp     dword ptr [rdx+rcx*4+8], 1F4h
0x1800cd196  cmovz   eax, r8d
0x1800cd19a  mov     [rdi+230h], eax
0x1800cd1a0  jmp     loc_1800CD00F
0x1800cd1a5  mov     r9d, 8000h
0x1800cd1ab  lea     r8, [rbp+arg_18]
0x1800cd1af  lea     rdx, [rbp+var_38]
0x1800cd1b3  mov     rcx, r13
0x1800cd1b6  call    ZwFreeVirtualMemory
0x1800cd1bb  jmp     loc_1800CD0EC
```
