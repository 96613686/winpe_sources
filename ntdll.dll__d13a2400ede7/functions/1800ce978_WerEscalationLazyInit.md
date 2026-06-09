# WerEscalationLazyInit

- ea: `0x1800ce978`
- end: `0x1800ced50`
- name: `WerEscalationLazyInit`
- size: `984`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ce640`
- `0x1800ce690`

## callees

- `0x180014e60`
- `0x180015710`
- `0x1800773d0`
- `0x1800ce978`
- `0x1800cf0d0`
- `0x1800cf5cc`
- `0x18011fb6c`
- `0x18013a99c`
- `0x18015ecc0`
- `0x18015ede0`
- `0x18015eea0`
- `0x18015ef00`
- `0x180161130`

## string_xrefs

- `0x1800cebe7`: `\REGISTRY\USER\`

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
0x1800ce978  push    rbp
0x1800ce97a  push    rbx
0x1800ce97b  push    rsi
0x1800ce97c  push    rdi
0x1800ce97d  push    r12
0x1800ce97f  push    r13
0x1800ce981  push    r14
0x1800ce983  push    r15
0x1800ce985  mov     rbp, rsp
0x1800ce988  sub     rsp, 68h
0x1800ce98c  mov     rax, cs:g_werEscalationData
0x1800ce993  xor     r12d, r12d
0x1800ce996  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800ce99a  mov     [rbp+Handle], r12
0x1800ce99e  mov     [rbp+arg_0], r12d
0x1800ce9a2  xorps   xmm0, xmm0
0x1800ce9a5  mov     [rbp+arg_8], r12d
0x1800ce9a9  xorps   xmm1, xmm1
0x1800ce9ac  mov     [rbp+arg_18], r12
0x1800ce9b0  mov     [rbp+var_38], r12
0x1800ce9b4  mov     [rbp+arg_10], r12d
0x1800ce9b8  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800ce9bc  movups  [rbp+var_18], xmm1
0x1800ce9c0  test    rax, rax
0x1800ce9c3  jnz     loc_1800CECA0
0x1800ce9c9  cmp     cs:g_disableEscalation, r12d
0x1800ce9d0  mov     ebx, 0C0000001h
0x1800ce9d5  mov     rdi, r12
0x1800ce9d8  jz      loc_1800CECB1
0x1800ce9de  test    rax, rax
0x1800ce9e1  jnz     loc_1800CEC68
0x1800ce9e7  mov     [rsp+68h+var_40], 4
0x1800ce9ef  lea     r9, [rbp+arg_18]
0x1800ce9f3  xor     r8d, r8d
0x1800ce9f6  mov     dword ptr [rsp+68h+var_48], 1000h
0x1800ce9fe  lea     rdx, [rbp+var_38]
0x1800cea02  mov     [rbp+arg_18], 238h
0x1800cea0a  mov     rcx, r13
0x1800cea0d  mov     [rbp+var_38], r12
0x1800cea11  call    ZwAllocateVirtualMemory
0x1800cea16  mov     ebx, eax
0x1800cea18  test    eax, eax
0x1800cea1a  js      loc_1800CEC7C
0x1800cea20  mov     rdi, [rbp+var_38]
0x1800cea24  mov     r14, [rbp+arg_18]
0x1800cea28  add     r14, rdi
0x1800cea2b  lea     rsi, [rdi+238h]
0x1800cea32  cmp     rsi, r14
0x1800cea35  ja      loc_1800CECC8
0x1800cea3b  mov     rax, gs:60h
0x1800cea44  mov     edx, 104h
0x1800cea49  mov     rcx, [rax+20h]
0x1800cea4d  mov     rax, gs:60h
0x1800cea56  movzx   r11d, word ptr [rcx+60h]
0x1800cea5b  mov     rcx, [rax+20h]
0x1800cea5f  mov     rax, rdi
0x1800cea62  shr     r11d, 1
0x1800cea65  mov     r9, [rcx+68h]
0x1800cea69  mov     ecx, 7FFFFFFEh
0x1800cea6e  mov     r8, r9
0x1800cea71  test    rcx, rcx
0x1800cea74  jz      short loc_1800CEA95
0x1800cea76  movzx   r10d, word ptr [r8]
0x1800cea7a  test    r10w, r10w
0x1800cea7e  jz      short loc_1800CEA95
0x1800cea80  mov     [rax], r10w
0x1800cea84  add     r8, 2
0x1800cea88  add     rax, 2
0x1800cea8c  dec     rcx
0x1800cea8f  sub     rdx, 1
0x1800cea93  jnz     short loc_1800CEA71
0x1800cea95  test    rdx, rdx
0x1800cea98  lea     rcx, [rax-2]
0x1800cea9c  cmovnz  rcx, rax
0x1800ceaa0  mov     [rcx], r12w
0x1800ceaa4  lea     rcx, [r9-2]
0x1800ceaa8  lea     rcx, [rcx+r11*2]
0x1800ceaac  cmp     rcx, r9
0x1800ceaaf  ja      loc_1800CECCF
0x1800ceab5  mov     rax, rcx
0x1800ceab8  sub     rax, r9
0x1800ceabb  sar     rax, 1
0x1800ceabe  sub     r11d, eax
0x1800ceac1  mov     edx, r11d
0x1800ceac4  call    HashStringToDwordCaseInsensitiveLen
0x1800ceac9  mov     [rdi+208h], eax
0x1800ceacf  lea     r8, [rbp+var_18]
0x1800cead3  mov     rcx, gs:60h
0x1800ceadc  xor     edx, edx
0x1800ceade  mov     rcx, [rcx+10h]
0x1800ceae2  call    WerEscalationReadImageVersionInfoForModuleBaseSafe
0x1800ceae7  mov     eax, dword ptr [rbp+var_18]
0x1800ceaea  lea     r8, [rbp+Handle]
0x1800ceaee  mov     [rdi+214h], eax
0x1800ceaf4  mov     edx, 8
0x1800ceaf9  mov     eax, dword ptr [rbp+var_18+8]
0x1800ceafc  mov     rcx, r13
0x1800ceaff  mov     [rdi+20Ch], eax
0x1800ceb05  mov     eax, dword ptr [rbp+var_18+0Ch]
0x1800ceb08  mov     [rdi+210h], eax
0x1800ceb0e  call    NtOpenProcessToken
0x1800ceb13  mov     ebx, eax
0x1800ceb15  test    eax, eax
0x1800ceb17  js      loc_1800CEC73
0x1800ceb1d  mov     rcx, [rbp+Handle]
0x1800ceb21  lea     rax, [rbp+arg_0]
0x1800ceb25  mov     r9d, r14d
0x1800ceb28  mov     [rsp+68h+var_48], rax
0x1800ceb2d  sub     r9d, esi
0x1800ceb30  mov     r8, rsi
0x1800ceb33  mov     edx, 1
0x1800ceb38  mov     [rbp+arg_0], r9d
0x1800ceb3c  call    NtQueryInformationToken
0x1800ceb41  mov     ebx, eax
0x1800ceb43  test    eax, eax
0x1800ceb45  js      loc_1800CEC73
0x1800ceb4b  mov     eax, [rbp+arg_0]
0x1800ceb4e  add     rax, 7
0x1800ceb52  shr     rax, 3
0x1800ceb56  lea     r15, [rsi+rax*8]
0x1800ceb5a  cmp     r15, r14
0x1800ceb5d  ja      loc_1800CECC8
0x1800ceb63  mov     rax, [rsi]
0x1800ceb66  lea     r8, [rbp+arg_8]
0x1800ceb6a  mov     [rdi+218h], rax
0x1800ceb71  mov     r9d, 4
0x1800ceb77  mov     dword ptr [rdi+230h], 40000000h
0x1800ceb81  lea     rax, [rbp+arg_0]
0x1800ceb85  mov     rcx, [rbp+Handle]
0x1800ceb89  mov     [rsp+68h+var_48], rax
0x1800ceb8e  lea     edx, [r9+0Eh]
0x1800ceb92  call    NtQueryInformationToken
0x1800ceb97  test    eax, eax
0x1800ceb99  jns     loc_1800CECED
0x1800ceb9f  mov     rcx, [rdi+218h]
0x1800ceba6  lea     rdx, [rbp+arg_10]
0x1800cebaa  call    RtlLengthSidAsUnicodeString
0x1800cebaf  mov     ebx, eax
0x1800cebb1  test    eax, eax
0x1800cebb3  js      loc_1800CEC73
0x1800cebb9  mov     ebx, [rbp+arg_10]
0x1800cebbc  lea     rsi, [rdi+220h]
0x1800cebc3  mov     [rsi], r12w
0x1800cebc7  mov     [rdi+228h], r15
0x1800cebce  lea     eax, [rbx+5Ah]
0x1800cebd1  movzx   ecx, ax
0x1800cebd4  mov     [rdi+222h], cx
0x1800cebdb  add     rcx, r15
0x1800cebde  cmp     rcx, r14
0x1800cebe1  ja      loc_1800CECC8
0x1800cebe7  lea     rdx, aRegistryUser; "\\REGISTRY\\USER\\"
0x1800cebee  mov     rcx, rsi
0x1800cebf1  call    RtlAppendUnicodeToString
0x1800cebf6  movzx   ecx, word ptr [rsi]
0x1800cebf9  xor     r8d, r8d; AllocateDestinationString
0x1800cebfc  mov     rax, [rdi+228h]
0x1800cec03  mov     rdx, [rdi+218h]; Sid
0x1800cec0a  shr     rcx, 1
0x1800cec0d  mov     [rbp+UnicodeString.MaximumLength], bx
0x1800cec11  mov     [rbp+UnicodeString.Length], r12w
0x1800cec16  lea     rcx, [rax+rcx*2]
0x1800cec1a  mov     [rbp+UnicodeString.Buffer], rcx
0x1800cec1e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800cec22  call    RtlConvertSidToUnicodeString
0x1800cec27  mov     ebx, eax
0x1800cec29  test    eax, eax
0x1800cec2b  js      short loc_1800CEC73
0x1800cec2d  movzx   eax, [rbp+UnicodeString.Length]
0x1800cec31  lea     rdx, aSoftwareMicros_1; "\\Software\\Microsoft\\Windows"
0x1800cec38  add     [rsi], ax
0x1800cec3b  mov     rcx, rsi
0x1800cec3e  call    RtlAppendUnicodeToString
0x1800cec43  mov     ebx, eax
0x1800cec45  test    eax, eax
0x1800cec47  js      short loc_1800CEC73
0x1800cec49  call    WerpEscalationIsWMRSendStringSet
0x1800cec4e  mov     [rdi+234h], eax
0x1800cec54  xor     eax, eax
0x1800cec56  lock cmpxchg cs:g_werEscalationData, rdi
0x1800cec5f  neg     rax
0x1800cec62  sbb     rcx, rcx
0x1800cec65  and     rdi, rcx
0x1800cec68  cmp     cs:g_sqmSessionHandle, r13
0x1800cec6f  cmovnz  ebx, r12d
0x1800cec73  test    rdi, rdi
0x1800cec76  jnz     loc_1800CED35
0x1800cec7c  mov     rcx, [rbp+Handle]; Handle
0x1800cec80  test    rcx, rcx
0x1800cec83  jnz     short loc_1800CEC99
0x1800cec85  mov     eax, ebx
0x1800cec87  add     rsp, 68h
0x1800cec8b  pop     r15
0x1800cec8d  pop     r14
0x1800cec8f  pop     r13
0x1800cec91  pop     r12
0x1800cec93  pop     rdi
0x1800cec94  pop     rsi
0x1800cec95  pop     rbx
0x1800cec96  pop     rbp
0x1800cec97  retn
0x1800cec99  call    NtClose
0x1800cec9e  jmp     short loc_1800CEC85
0x1800ceca0  cmp     cs:g_sqmSessionHandle, r13
0x1800ceca7  jz      loc_1800CE9C9
0x1800cecad  xor     eax, eax
0x1800cecaf  jmp     short loc_1800CEC87
0x1800cecb1  call    WerpEscalationIsDisabled
0x1800cecb6  mov     cs:g_disableEscalation, eax
0x1800cecbc  mov     rax, cs:g_werEscalationData
0x1800cecc3  jmp     loc_1800CE9DE
0x1800cecc8  mov     ebx, 0C0000023h
0x1800ceccd  jmp     short loc_1800CEC73
0x1800ceccf  cmp     word ptr [rcx], 5Ch ; '\'
0x1800cecd3  jz      short loc_1800CECE4
0x1800cecd5  cmp     word ptr [rcx], 2Fh ; '/'
0x1800cecd9  jz      short loc_1800CECE4
0x1800cecdb  sub     rcx, 2
0x1800cecdf  jmp     loc_1800CEAAC
0x1800cece4  add     rcx, 2
0x1800cece8  jmp     loc_1800CEAB5
0x1800ceced  cmp     [rbp+arg_8], 2
0x1800cecf1  jnz     short loc_1800CED02
0x1800cecf3  mov     dword ptr [rdi+230h], 0C0000000h
0x1800cecfd  jmp     loc_1800CEB9F
0x1800ced02  cmp     [rbp+arg_8], 1
0x1800ced06  jnz     loc_1800CEB9F
0x1800ced0c  mov     rdx, [rsi]
0x1800ced0f  mov     eax, r12d
0x1800ced12  mov     r8d, 80000000h
0x1800ced18  movzx   ecx, byte ptr [rdx+1]
0x1800ced1c  dec     ecx
0x1800ced1e  cmp     dword ptr [rdx+rcx*4+8], 1F4h
0x1800ced26  cmovz   eax, r8d
0x1800ced2a  mov     [rdi+230h], eax
0x1800ced30  jmp     loc_1800CEB9F
0x1800ced35  mov     r9d, 8000h
0x1800ced3b  lea     r8, [rbp+arg_18]
0x1800ced3f  lea     rdx, [rbp+var_38]
0x1800ced43  mov     rcx, r13
0x1800ced46  call    ZwFreeVirtualMemory
0x1800ced4b  jmp     loc_1800CEC7C
```
