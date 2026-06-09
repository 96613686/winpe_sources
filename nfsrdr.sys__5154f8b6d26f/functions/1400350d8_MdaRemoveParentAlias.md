# MdaRemoveParentAlias

- ea: `0x1400350d8`
- end: `0x14003537e`
- name: `MdaRemoveParentAlias`
- size: `678`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400350d8`
- `0x140035384`

## callees

- `0x140009380`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x1400350d8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140035326`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140035326`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003529d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400352dc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140035339`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003529d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400352dc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140035339`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400351f4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140035283`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400351f4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140035283`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035168`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003517f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035168`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003517f`

## pseudocode

```c
__int64 __fastcall MdaRemoveParentAlias(__int64 a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS appended; // edi
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  NTSTATUS v8; // ebx
  UNICODE_STRING String1; // [rsp+20h] [rbp-48h] BYREF
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-18h] BYREF

  v10 = 0;
  String1 = 0;
  DestinationString = 0;
  String2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids, a1);
  }
  RtlInitUnicodeString(&DestinationString, L"..");
  RtlInitUnicodeString(&String2, L".");
  MdaDissectNameTail(a1, &v10, &String1);
  if ( (_WORD)v10 )
  {
    appended = MdaRemoveParentAlias(&v10, a2);
    if ( appended < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)appended;
      v6 = 41;
LABEL_12:
      WPP_SF_d(v5->AttachedDevice, v6, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids);
      return (unsigned int)appended;
    }
    if ( RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
    {
      if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
      {
        appended = RtlAppendUnicodeStringToString(a2, &Slash);
        if ( appended < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            return (unsigned int)appended;
          }
          v6 = 43;
          goto LABEL_12;
        }
        appended = RtlAppendUnicodeStringToString(a2, &String1);
        if ( appended < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            return (unsigned int)appended;
          }
          v6 = 44;
          goto LABEL_12;
        }
      }
    }
    else
    {
      MdaDissectNameTail(a2, &v10, &String1);
      a2->Length = v10;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids, a2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids);
    }
    return 0;
  }
  a2->Length = 0;
  RtlCopyUnicodeString(a2, &Slash);
  v8 = RtlAppendUnicodeStringToString(a2, &String1);
  if ( v8 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400350d8  push    rbp
0x1400350da  push    rbx
0x1400350db  push    rsi
0x1400350dc  push    rdi
0x1400350dd  push    r14
0x1400350df  push    r15
0x1400350e1  mov     rbp, rsp
0x1400350e4  sub     rsp, 68h
0x1400350e8  xorps   xmm0, xmm0
0x1400350eb  xorps   xmm1, xmm1
0x1400350ee  movups  [rbp+var_38], xmm0
0x1400350f2  mov     rbx, rdx
0x1400350f5  mov     rdi, rcx
0x1400350f8  movups  xmmword ptr [rbp+String1.Length], xmm1
0x1400350fc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140035100  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140035104  mov     rcx, cs:WPP_GLOBAL_Control
0x14003510b  lea     rsi, WPP_GLOBAL_Control
0x140035112  lea     r14, WPP_32f1620f80ee32af50b0eb5116009540_Traceguids
0x140035119  cmp     rcx, rsi
0x14003511c  jz      short loc_14003515D
0x14003511e  mov     eax, [rcx+2Ch]
0x140035121  test    al, 8
0x140035123  jz      short loc_140035136
0x140035125  mov     rcx, [rcx+18h]
0x140035129  mov     edx, 27h ; '''
0x14003512e  mov     r8, r14
0x140035131  call    WPP_SF_
0x140035136  mov     rcx, cs:WPP_GLOBAL_Control
0x14003513d  cmp     rcx, rsi
0x140035140  jz      short loc_14003515D
0x140035142  mov     eax, [rcx+2Ch]
0x140035145  test    al, 4
0x140035147  jz      short loc_14003515D
0x140035149  mov     rcx, [rcx+18h]
0x14003514d  mov     edx, 28h ; '('
0x140035152  mov     r9, rdi
0x140035155  mov     r8, r14
0x140035158  call    WPP_SF_Z
0x14003515d  lea     rdx, asc_14003DF04; ".."
0x140035164  lea     rcx, [rbp+DestinationString]; DestinationString
0x140035168  call    cs:__imp_RtlInitUnicodeString
0x14003516f  nop     dword ptr [rax+rax+00h]
0x140035174  lea     rdx, asc_14003DF0C; "."
0x14003517b  lea     rcx, [rbp+String2]; DestinationString
0x14003517f  call    cs:__imp_RtlInitUnicodeString
0x140035186  nop     dword ptr [rax+rax+00h]
0x14003518b  lea     r8, [rbp+String1]
0x14003518f  mov     rcx, rdi
0x140035192  lea     rdx, [rbp+var_38]
0x140035196  call    MdaDissectNameTail
0x14003519b  xor     r15d, r15d
0x14003519e  cmp     word ptr [rbp+var_38], r15w
0x1400351a3  jz      loc_140035318
0x1400351a9  mov     rdx, rbx
0x1400351ac  lea     rcx, [rbp+var_38]
0x1400351b0  call    MdaRemoveParentAlias
0x1400351b5  mov     edi, eax
0x1400351b7  test    eax, eax
0x1400351b9  jns     short loc_1400351E9
0x1400351bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400351c2  cmp     rcx, rsi
0x1400351c5  jz      short loc_1400351E2
0x1400351c7  mov     edx, [rcx+2Ch]
0x1400351ca  test    dl, 1
0x1400351cd  jz      short loc_1400351E2
0x1400351cf  lea     edx, [r15+29h]
0x1400351d3  mov     rcx, [rcx+18h]
0x1400351d7  mov     r9d, edi
0x1400351da  mov     r8, r14
0x1400351dd  call    WPP_SF_d
0x1400351e2  mov     eax, edi
0x1400351e4  jmp     loc_14003526A
0x1400351e9  mov     r8b, 1; CaseInSensitive
0x1400351ec  lea     rdx, [rbp+DestinationString]; String2
0x1400351f0  lea     rcx, [rbp+String1]; String1
0x1400351f4  call    cs:__imp_RtlCompareUnicodeString
0x1400351fb  nop     dword ptr [rax+rax+00h]
0x140035200  test    eax, eax
0x140035202  jnz     short loc_140035278
0x140035204  lea     r8, [rbp+String1]
0x140035208  mov     rcx, rbx
0x14003520b  lea     rdx, [rbp+var_38]
0x14003520f  call    MdaDissectNameTail
0x140035214  movzx   r11d, word ptr [rbp+var_38]
0x140035219  mov     [rbx], r11w
0x14003521d  mov     rcx, cs:WPP_GLOBAL_Control
0x140035224  cmp     rcx, rsi
0x140035227  jz      short loc_140035268
0x140035229  mov     eax, [rcx+2Ch]
0x14003522c  test    al, 4
0x14003522e  jz      short loc_140035244
0x140035230  mov     rcx, [rcx+18h]
0x140035234  mov     edx, 2Dh ; '-'
0x140035239  mov     r9, rbx
0x14003523c  mov     r8, r14
0x14003523f  call    WPP_SF_Z
0x140035244  mov     rcx, cs:WPP_GLOBAL_Control
0x14003524b  cmp     rcx, rsi
0x14003524e  jz      short loc_140035268
0x140035250  mov     eax, [rcx+2Ch]
0x140035253  test    al, 8
0x140035255  jz      short loc_140035268
0x140035257  mov     rcx, [rcx+18h]
0x14003525b  mov     edx, 2Eh ; '.'
0x140035260  mov     r8, r14
0x140035263  call    WPP_SF_
0x140035268  xor     eax, eax
0x14003526a  add     rsp, 68h
0x14003526e  pop     r15
0x140035270  pop     r14
0x140035272  pop     rdi
0x140035273  pop     rsi
0x140035274  pop     rbx
0x140035275  pop     rbp
0x140035276  retn
0x140035278  mov     r8b, 1; CaseInSensitive
0x14003527b  lea     rdx, [rbp+String2]; String2
0x14003527f  lea     rcx, [rbp+String1]; String1
0x140035283  call    cs:__imp_RtlCompareUnicodeString
0x14003528a  nop     dword ptr [rax+rax+00h]
0x14003528f  test    eax, eax
0x140035291  jz      short loc_14003521D
0x140035293  lea     rdx, Slash; Source
0x14003529a  mov     rcx, rbx; Destination
0x14003529d  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400352a4  nop     dword ptr [rax+rax+00h]
0x1400352a9  mov     edi, eax
0x1400352ab  test    eax, eax
0x1400352ad  jns     short loc_1400352D5
0x1400352af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352b6  cmp     rcx, rsi
0x1400352b9  jz      loc_1400351E2
0x1400352bf  mov     edx, [rcx+2Ch]
0x1400352c2  test    dl, 1
0x1400352c5  jz      loc_1400351E2
0x1400352cb  mov     edx, 2Bh ; '+'
0x1400352d0  jmp     loc_1400351D3
0x1400352d5  lea     rdx, [rbp+String1]; Source
0x1400352d9  mov     rcx, rbx; Destination
0x1400352dc  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400352e3  nop     dword ptr [rax+rax+00h]
0x1400352e8  mov     edi, eax
0x1400352ea  test    eax, eax
0x1400352ec  jns     loc_14003521D
0x1400352f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352f9  cmp     rcx, rsi
0x1400352fc  jz      loc_1400351E2
0x140035302  mov     edx, [rcx+2Ch]
0x140035305  test    dl, 1
0x140035308  jz      loc_1400351E2
0x14003530e  mov     edx, 2Ch ; ','
0x140035313  jmp     loc_1400351D3
0x140035318  lea     rdx, Slash; SourceString
0x14003531f  mov     [rbx], r15w
0x140035323  mov     rcx, rbx; DestinationString
0x140035326  call    cs:__imp_RtlCopyUnicodeString
0x14003532d  nop     dword ptr [rax+rax+00h]
0x140035332  lea     rdx, [rbp+String1]; Source
0x140035336  mov     rcx, rbx; Destination
0x140035339  call    cs:__imp_RtlAppendUnicodeStringToString
0x140035340  nop     dword ptr [rax+rax+00h]
0x140035345  mov     ebx, eax
0x140035347  test    eax, eax
0x140035349  jns     loc_140035268
0x14003534f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035356  cmp     rcx, rsi
0x140035359  jz      short loc_140035377
0x14003535b  mov     edx, [rcx+2Ch]
0x14003535e  test    dl, 1
0x140035361  jz      short loc_140035377
0x140035363  mov     rcx, [rcx+18h]
0x140035367  mov     edx, 2Ah ; '*'
0x14003536c  mov     r9d, eax
0x14003536f  mov     r8, r14
0x140035372  call    WPP_SF_d
0x140035377  mov     eax, ebx
0x140035379  jmp     loc_14003526A
```
