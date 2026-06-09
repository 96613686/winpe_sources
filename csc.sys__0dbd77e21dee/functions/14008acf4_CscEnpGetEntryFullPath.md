# CscEnpGetEntryFullPath

- ea: `0x14008acf4`
- end: `0x14008afa7`
- name: `CscEnpGetEntryFullPath`
- size: `691`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140012250`
- `0x140081874`

## callees

- `0x140012c60`
- `0x140018fd0`
- `0x14002f010`
- `0x14002f440`
- `0x14008acf4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008ad96`
- `ntoskrnl!ExAllocatePool2` at `0x14008ae68`
- `ntoskrnl!ExAllocatePool2` at `0x14008ad96`
- `ntoskrnl!ExAllocatePool2` at `0x14008ae68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008af26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008af26`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008aecc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008aee9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008aecc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008aee9`

## pseudocode

```c
__int64 __fastcall CscEnpGetEntryFullPath(__int64 a1, struct _UNICODE_STRING *a2)
{
  signed int v4; // esi
  USHORT v5; // r14
  PWSTR Buffer; // r13
  _OWORD *v7; // rdi
  int v8; // ebx
  __int64 i; // rcx
  _OWORD *Pool2; // rax
  NTSTATUS appended; // ebx
  __int64 j; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  int k; // esi
  __int64 v16; // rax
  UNICODE_STRING Source; // [rsp+30h] [rbp-99h] BYREF
  _OWORD P[10]; // [rsp+40h] [rbp-89h] BYREF

  v4 = 0;
  v5 = 0;
  memset(P, 0, sizeof(P));
  Buffer = a2->Buffer;
  v7 = P;
  v8 = 20;
  for ( i = a1; i; ++v4 )
  {
    if ( (unsigned int)v4 < 0x14 )
    {
      *((_QWORD *)P + v4) = i;
      v5 += *(_WORD *)(i + 48) + 2;
    }
    i = *(_QWORD *)(i + 24);
  }
  if ( (unsigned __int64)v4 > 0x14 )
  {
    Pool2 = (_OWORD *)ExAllocatePool2(256, 8LL * v4, 557871939);
    v7 = Pool2;
    if ( !Pool2 )
    {
      appended = -1073741670;
LABEL_31:
      CscEnpFreeEntryFullPath((__int64)a2, Buffer);
      goto LABEL_32;
    }
    *Pool2 = P[0];
    Pool2[1] = P[1];
    Pool2[2] = P[2];
    Pool2[3] = P[3];
    Pool2[4] = P[4];
    Pool2[5] = P[5];
    Pool2[6] = P[6];
    Pool2[7] = P[7];
    Pool2[8] = P[8];
    Pool2[9] = P[9];
    for ( j = *(_QWORD *)(*((_QWORD *)&P[9] + 1) + 24LL); j; j = *(_QWORD *)(j + 24) )
    {
      if ( v8 >= 0 && v8 < v4 )
      {
        v13 = v8++;
        *((_QWORD *)v7 + v13) = j;
        v5 += *(_WORD *)(j + 48) + 2;
      }
    }
  }
  a2->Length = 0;
  if ( v5 <= a2->MaximumLength
    || (a2->MaximumLength = v5, v14 = ExAllocatePool2(258, v5, 557871939), (a2->Buffer = (PWSTR)v14) != 0) )
  {
    if ( v4 )
    {
      *(_QWORD *)&Source.Length = 262146;
      Source.Buffer = L"\\";
      appended = 0;
      for ( k = v4 - 1; k >= 0; --k )
      {
        v16 = *((_QWORD *)v7 + k);
        if ( v16 && *(_WORD *)(v16 + 48) )
        {
          appended = RtlAppendUnicodeStringToString(a2, &Source);
          if ( appended < 0 )
            goto LABEL_27;
          appended = RtlAppendUnicodeStringToString(a2, (PCUNICODE_STRING)(*((_QWORD *)v7 + k) + 48LL));
        }
        if ( appended < 0 )
          goto LABEL_27;
      }
    }
    appended = 0;
  }
  else
  {
    appended = -1073741670;
  }
LABEL_27:
  if ( v7 && v7 != P )
    ExFreePoolWithTag(v7, 0x21407343u);
  if ( appended < 0 )
    goto LABEL_31;
LABEL_32:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f12c405b2c6e3bfd8040ffe298a585bc_Traceguids);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14008acf4  mov     [rsp-8+arg_10], rbx
0x14008acf9  push    rbp
0x14008acfa  push    rsi
0x14008acfb  push    rdi
0x14008acfc  push    r12
0x14008acfe  push    r13
0x14008ad00  push    r14
0x14008ad02  push    r15
0x14008ad04  lea     rbp, [rsp-27h]
0x14008ad09  sub     rsp, 0F0h
0x14008ad10  mov     rax, cs:__security_cookie
0x14008ad17  xor     rax, rsp
0x14008ad1a  mov     [rbp+57h+var_40], rax
0x14008ad1e  mov     r15, rdx
0x14008ad21  mov     r12, rcx
0x14008ad24  xor     edx, edx; Val
0x14008ad26  lea     rcx, [rsp+120h+P]; void *
0x14008ad2b  mov     r8d, 0A0h; Size
0x14008ad31  xor     esi, esi
0x14008ad33  xor     r14d, r14d
0x14008ad36  call    memset
0x14008ad3b  mov     r13, [r15+8]
0x14008ad3f  lea     rdi, [rsp+120h+P]
0x14008ad44  xor     r8d, r8d
0x14008ad47  lea     ebx, [rsi+14h]
0x14008ad4a  lea     edx, [rsi+2]
0x14008ad4d  mov     rcx, r12
0x14008ad50  test    r12, r12
0x14008ad53  jz      short loc_14008AD7B
0x14008ad55  test    esi, esi
0x14008ad57  js      short loc_14008AD70
0x14008ad59  cmp     esi, ebx
0x14008ad5b  jnb     short loc_14008AD70
0x14008ad5d  movsxd  rax, esi
0x14008ad60  mov     qword ptr [rsp+rax*8+120h+P], rcx
0x14008ad65  movzx   eax, word ptr [rcx+30h]
0x14008ad69  add     ax, dx
0x14008ad6c  add     r14w, ax
0x14008ad70  mov     rcx, [rcx+18h]
0x14008ad74  inc     esi
0x14008ad76  test    rcx, rcx
0x14008ad79  jnz     short loc_14008AD55
0x14008ad7b  movsxd  rdx, esi
0x14008ad7e  cmp     rdx, rbx
0x14008ad81  jbe     loc_14008AE49
0x14008ad87  shl     rdx, 3
0x14008ad8b  mov     ecx, 100h
0x14008ad90  mov     r8d, 21407343h
0x14008ad96  call    cs:__imp_ExAllocatePool2
0x14008ad9d  nop     dword ptr [rax+rax+00h]
0x14008ada2  xor     r8d, r8d
0x14008ada5  mov     rdi, rax
0x14008ada8  test    rax, rax
0x14008adab  jnz     short loc_14008ADBC
0x14008adad  mov     ebx, 0C000009Ah
0x14008adb2  mov     esi, 123h
0x14008adb7  jmp     loc_14008AF36
0x14008adbc  movups  xmm0, [rsp+120h+P]
0x14008adc1  movups  xmmword ptr [rax], xmm0
0x14008adc4  movups  xmm1, [rbp+57h+var_D0]
0x14008adc8  movups  xmmword ptr [rax+10h], xmm1
0x14008adcc  movups  xmm0, [rbp+57h+var_C0]
0x14008add0  movups  xmmword ptr [rax+20h], xmm0
0x14008add4  movups  xmm1, [rbp+57h+var_B0]
0x14008add8  movups  xmmword ptr [rax+30h], xmm1
0x14008addc  movups  xmm0, [rbp+57h+var_A0]
0x14008ade0  movups  xmmword ptr [rax+40h], xmm0
0x14008ade4  movups  xmm1, [rbp+57h+var_90]
0x14008ade8  movups  xmmword ptr [rax+50h], xmm1
0x14008adec  movups  xmm0, [rbp+57h+var_80]
0x14008adf0  movups  xmmword ptr [rax+60h], xmm0
0x14008adf4  movups  xmm1, [rbp+57h+var_70]
0x14008adf8  movups  xmmword ptr [rax+70h], xmm1
0x14008adfc  movups  xmm0, [rbp+57h+var_60]
0x14008ae00  movups  xmmword ptr [rax+80h], xmm0
0x14008ae07  movups  xmm1, [rbp+57h+var_50]
0x14008ae0b  movups  xmmword ptr [rax+90h], xmm1
0x14008ae12  mov     rax, qword ptr [rbp+57h+var_50+8]
0x14008ae16  mov     rcx, [rax+18h]
0x14008ae1a  test    rcx, rcx
0x14008ae1d  jz      short loc_14008AE49
0x14008ae1f  mov     edx, 2
0x14008ae24  test    ebx, ebx
0x14008ae26  js      short loc_14008AE40
0x14008ae28  cmp     ebx, esi
0x14008ae2a  jge     short loc_14008AE40
0x14008ae2c  movsxd  rax, ebx
0x14008ae2f  inc     ebx
0x14008ae31  mov     [rdi+rax*8], rcx
0x14008ae35  movzx   eax, word ptr [rcx+30h]
0x14008ae39  add     ax, dx
0x14008ae3c  add     r14w, ax
0x14008ae40  mov     rcx, [rcx+18h]
0x14008ae44  test    rcx, rcx
0x14008ae47  jnz     short loc_14008AE24
0x14008ae49  mov     [r15], r8w
0x14008ae4d  cmp     r14w, [r15+2]
0x14008ae52  jbe     short loc_14008AE8F
0x14008ae54  movzx   edx, r14w
0x14008ae58  mov     ecx, 102h
0x14008ae5d  mov     r8d, 21407343h
0x14008ae63  mov     [r15+2], r14w
0x14008ae68  call    cs:__imp_ExAllocatePool2
0x14008ae6f  nop     dword ptr [rax+rax+00h]
0x14008ae74  xor     r8d, r8d
0x14008ae77  mov     [r15+8], rax
0x14008ae7b  test    rax, rax
0x14008ae7e  jnz     short loc_14008AE8F
0x14008ae80  mov     ebx, 0C000009Ah
0x14008ae85  mov     esi, 158h
0x14008ae8a  jmp     loc_14008AF0F
0x14008ae8f  test    esi, esi
0x14008ae91  jz      short loc_14008AF09
0x14008ae93  lea     rax, asc_1400325C0; "\\"
0x14008ae9a  mov     qword ptr [rsp+120h+Source.Length], 40002h
0x14008aea3  mov     [rsp+120h+Source.Buffer], rax
0x14008aea8  mov     ebx, r8d
0x14008aeab  dec     esi
0x14008aead  test    esi, esi
0x14008aeaf  js      short loc_14008AF09
0x14008aeb1  movsxd  r14, esi
0x14008aeb4  mov     rax, [rdi+r14*8]
0x14008aeb8  test    rax, rax
0x14008aebb  jz      short loc_14008AEFA
0x14008aebd  cmp     [rax+30h], r8w
0x14008aec2  jz      short loc_14008AEFA
0x14008aec4  lea     rdx, [rsp+120h+Source]; Source
0x14008aec9  mov     rcx, r15; Destination
0x14008aecc  call    cs:__imp_RtlAppendUnicodeStringToString
0x14008aed3  nop     dword ptr [rax+rax+00h]
0x14008aed8  mov     ebx, eax
0x14008aeda  test    eax, eax
0x14008aedc  js      short loc_14008AF02
0x14008aede  mov     rdx, [rdi+r14*8]
0x14008aee2  mov     rcx, r15; Destination
0x14008aee5  add     rdx, 30h ; '0'; Source
0x14008aee9  call    cs:__imp_RtlAppendUnicodeStringToString
0x14008aef0  nop     dword ptr [rax+rax+00h]
0x14008aef5  mov     ebx, eax
0x14008aef7  xor     r8d, r8d
0x14008aefa  test    ebx, ebx
0x14008aefc  js      short loc_14008AF02
0x14008aefe  dec     esi
0x14008af00  jmp     short loc_14008AEAD
0x14008af02  mov     esi, 173h
0x14008af07  jmp     short loc_14008AF0F
0x14008af09  mov     esi, r8d
0x14008af0c  mov     ebx, r8d
0x14008af0f  test    rdi, rdi
0x14008af12  jz      short loc_14008AF32
0x14008af14  lea     rax, [rsp+120h+P]
0x14008af19  cmp     rdi, rax
0x14008af1c  jz      short loc_14008AF32
0x14008af1e  mov     edx, 21407343h; Tag
0x14008af23  mov     rcx, rdi; P
0x14008af26  call    cs:__imp_ExFreePoolWithTag
0x14008af2d  nop     dword ptr [rax+rax+00h]
0x14008af32  test    ebx, ebx
0x14008af34  jns     short loc_14008AF41
0x14008af36  mov     rdx, r13
0x14008af39  mov     rcx, r15
0x14008af3c  call    CscEnpFreeEntryFullPath
0x14008af41  mov     rcx, cs:WPP_GLOBAL_Control
0x14008af48  lea     rax, WPP_GLOBAL_Control
0x14008af4f  cmp     rcx, rax
0x14008af52  jz      short loc_14008AF7D
0x14008af54  test    dword ptr [rcx+2Ch], 40000h
0x14008af5b  jz      short loc_14008AF7D
0x14008af5d  mov     rcx, [rcx+18h]
0x14008af61  lea     r8, WPP_f12c405b2c6e3bfd8040ffe298a585bc_Traceguids
0x14008af68  mov     edx, 0Ah
0x14008af6d  mov     [rsp+120h+var_F8], ebx
0x14008af71  mov     r9, r12
0x14008af74  mov     [rsp+120h+var_100], esi
0x14008af78  call    WPP_SF_qDD
0x14008af7d  mov     eax, ebx
0x14008af7f  mov     rcx, [rbp+57h+var_40]
0x14008af83  xor     rcx, rsp; StackCookie
0x14008af86  call    __security_check_cookie
0x14008af8b  mov     rbx, [rsp+120h+arg_10]
0x14008af93  add     rsp, 0F0h
0x14008af9a  pop     r15
0x14008af9c  pop     r14
0x14008af9e  pop     r13
0x14008afa0  pop     r12
0x14008afa2  pop     rdi
0x14008afa3  pop     rsi
0x14008afa4  pop     rbp
0x14008afa5  retn
```
