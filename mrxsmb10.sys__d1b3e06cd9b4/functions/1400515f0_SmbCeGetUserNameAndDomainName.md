# SmbCeGetUserNameAndDomainName

- ea: `0x1400515f0`
- end: `0x140051874`
- name: `SmbCeGetUserNameAndDomainName`
- size: `644`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c1f0`
- `0x140015ab8`
- `0x14003652c`
- `0x14004245c`

## callees

- `0x1400166c0`
- `0x1400515f0`

## import_xrefs

- `ntoskrnl!LsaFreeReturnBuffer` at `0x140051843`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140051843`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051775`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051775`
- `ksecdd!MapSecurityError` at `0x140051752`
- `ksecdd!MapSecurityError` at `0x140051752`
- `ksecdd!GetSecurityUserInfo` at `0x140051694`
- `ksecdd!GetSecurityUserInfo` at `0x140051694`
- `ksecdd!FreeContextBuffer` at `0x14005182a`
- `ksecdd!FreeContextBuffer` at `0x14005182a`
- `ksecdd!QueryContextAttributesW` at `0x140051744`
- `ksecdd!QueryContextAttributesW` at `0x140051744`

## pseudocode

```c
__int64 __fastcall SmbCeGetUserNameAndDomainName(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  SECURITY_STRING *p_LogonDomainName; // r14
  PSecurityUserData v8; // r15
  int v9; // ecx
  int v10; // ecx
  unsigned int SecurityUserInfo; // ebp
  unsigned int Length; // ecx
  unsigned int v13; // eax
  __int64 v14; // r14
  SECURITY_STATUS v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int16 v18; // ax
  __int128 v20; // [rsp+20h] [rbp-58h] BYREF
  __int128 v21; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  WCHAR *pBuffer; // [rsp+88h] [rbp+10h] BYREF
  PSecurityUserData UserInformation; // [rsp+90h] [rbp+18h] BYREF

  UserInformation = 0;
  pBuffer = 0;
  DestinationString = 0;
  v21 = 0;
  v20 = 0;
  if ( !a3 || !a4 || *(_WORD *)(a3 + 2) < 0x200u || *(_WORD *)(a4 + 2) < 0x1Eu )
    return 3221225485LL;
  p_LogonDomainName = 0;
  v8 = 0;
  v9 = a1 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 != 1 )
        goto LABEL_30;
      goto LABEL_8;
    }
  }
  else
  {
    v14 = *(_QWORD *)(a2 + 176);
    if ( v14 )
    {
      v8 = *(PSecurityUserData *)(v14 + 16);
      p_LogonDomainName = *(SECURITY_STRING **)(v14 + 32);
      if ( v8 && p_LogonDomainName )
      {
        SecurityUserInfo = 0;
        goto LABEL_10;
      }
    }
    else
    {
      p_LogonDomainName = 0;
    }
  }
  v15 = QueryContextAttributesW((PCtxtHandle)(a2 + 344), 1u, &pBuffer);
  SecurityUserInfo = MapSecurityError(v15);
  if ( !SecurityUserInfo )
  {
    RtlInitUnicodeString(&DestinationString, pBuffer);
    v16 = DestinationString.Length >> 1;
    v17 = 0;
    if ( v16 )
    {
      while ( DestinationString.Buffer[v17] != 92 )
      {
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= v16 )
          goto LABEL_23;
      }
      goto LABEL_24;
    }
LABEL_23:
    if ( (unsigned int)v17 < v16 )
    {
LABEL_24:
      if ( p_LogonDomainName )
      {
        v18 = v20;
      }
      else
      {
        *((_QWORD *)&v20 + 1) = DestinationString.Buffer;
        v18 = 2 * v17;
        p_LogonDomainName = (SECURITY_STRING *)&v20;
        WORD1(v20) = 2 * v17;
        LOWORD(v20) = 2 * v17;
      }
      if ( !v8 )
      {
        v8 = (PSecurityUserData)&v21;
        WORD1(v21) = DestinationString.Length - v18 - 2;
        LOWORD(v21) = WORD1(v21);
        *((_QWORD *)&v21 + 1) = &DestinationString.Buffer[v17 + 1];
      }
      goto LABEL_10;
    }
  }
LABEL_8:
  SecurityUserInfo = GetSecurityUserInfo((PLUID)(a2 + 144), 1u, &UserInformation);
  if ( !SecurityUserInfo )
  {
    v8 = UserInformation;
    p_LogonDomainName = &UserInformation->LogonDomainName;
LABEL_10:
    Length = v8->UserName.Length;
    if ( (unsigned __int16)Length > *(_WORD *)(a3 + 2) || p_LogonDomainName->Length > *(_WORD *)(a4 + 2) )
    {
      SecurityUserInfo = -2147483643;
    }
    else
    {
      *(_WORD *)a3 = Length;
      memmove(*(void **)(a3 + 8), v8->UserName.Buffer, Length);
      v13 = p_LogonDomainName->Length;
      *(_WORD *)a4 = v13;
      if ( (_WORD)v13 )
        memmove(*(void **)(a4 + 8), p_LogonDomainName->Buffer, v13);
    }
    goto LABEL_31;
  }
LABEL_30:
  SecurityUserInfo = -1073741726;
LABEL_31:
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  if ( UserInformation )
    LsaFreeReturnBuffer(UserInformation);
  return SecurityUserInfo;
}

```

## disassembly

```asm
0x1400515f0  mov     r11, rsp
0x1400515f3  push    rbx
0x1400515f4  push    rsi
0x1400515f5  push    rdi
0x1400515f6  push    r12
0x1400515f8  sub     rsp, 58h
0x1400515fc  xor     r12d, r12d
0x1400515ff  xorps   xmm0, xmm0
0x140051602  mov     [r11+18h], r12
0x140051606  xorps   xmm1, xmm1
0x140051609  mov     [r11+10h], r12
0x14005160d  mov     rdi, r9
0x140051610  mov     rbx, r8
0x140051613  mov     rsi, rdx
0x140051616  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14005161b  movups  [rsp+78h+var_48], xmm1
0x140051620  movups  [rsp+78h+var_58], xmm0
0x140051625  test    r8, r8
0x140051628  jz      loc_140051864
0x14005162e  test    r9, r9
0x140051631  jz      loc_140051864
0x140051637  mov     eax, 200h
0x14005163c  cmp     [r8+2], ax
0x140051641  jb      loc_140051864
0x140051647  cmp     word ptr [r9+2], 1Eh
0x14005164d  jb      loc_140051864
0x140051653  mov     [r11+20h], r14
0x140051657  mov     r14d, r12d
0x14005165a  mov     [r11-28h], r15
0x14005165e  mov     r15d, r12d
0x140051661  mov     [r11+8], rbp
0x140051665  sub     ecx, 1
0x140051668  jz      loc_14005170A
0x14005166e  sub     ecx, 1
0x140051671  jz      loc_140051730
0x140051677  cmp     ecx, 1
0x14005167a  jnz     loc_14005180B
0x140051680  lea     rcx, [rsi+90h]; LogonId
0x140051687  mov     edx, 1; Flags
0x14005168c  lea     r8, [rsp+78h+UserInformation]; UserInformation
0x140051694  call    cs:__imp_GetSecurityUserInfo
0x14005169b  nop     dword ptr [rax+rax+00h]
0x1400516a0  mov     ebp, eax
0x1400516a2  test    eax, eax
0x1400516a4  jnz     loc_14005180B
0x1400516aa  mov     r15, [rsp+78h+UserInformation]
0x1400516b2  lea     r14, [r15+10h]
0x1400516b6  movzx   ecx, word ptr [r15]
0x1400516ba  cmp     cx, [rbx+2]
0x1400516be  ja      loc_140051804
0x1400516c4  movzx   eax, word ptr [rdi+2]
0x1400516c8  cmp     [r14], ax
0x1400516cc  ja      loc_140051804
0x1400516d2  mov     [rbx], cx
0x1400516d5  mov     r8d, ecx; Size
0x1400516d8  mov     rdx, [r15+8]; Src
0x1400516dc  mov     rcx, [rbx+8]; void *
0x1400516e0  call    memmove
0x1400516e5  movzx   eax, word ptr [r14]
0x1400516e9  mov     [rdi], ax
0x1400516ec  test    ax, ax
0x1400516ef  jz      loc_140051810
0x1400516f5  mov     rdx, [r14+8]; Src
0x1400516f9  mov     r8d, eax; Size
0x1400516fc  mov     rcx, [rdi+8]; void *
0x140051700  call    memmove
0x140051705  jmp     loc_140051810
0x14005170a  mov     r14, [rdx+0B0h]
0x140051711  test    r14, r14
0x140051714  jz      short loc_14005172D
0x140051716  mov     r15, [r14+10h]
0x14005171a  mov     r14, [r14+20h]
0x14005171e  test    r15, r15
0x140051721  jz      short loc_140051730
0x140051723  test    r14, r14
0x140051726  jz      short loc_140051730
0x140051728  mov     ebp, r12d
0x14005172b  jmp     short loc_1400516B6
0x14005172d  mov     r14, r12
0x140051730  lea     rcx, [rdx+158h]; phContext
0x140051737  mov     edx, 1; ulAttribute
0x14005173c  lea     r8, [rsp+78h+pBuffer]; pBuffer
0x140051744  call    cs:__imp_QueryContextAttributesW
0x14005174b  nop     dword ptr [rax+rax+00h]
0x140051750  mov     ecx, eax; SecStatus
0x140051752  call    cs:__imp_MapSecurityError
0x140051759  nop     dword ptr [rax+rax+00h]
0x14005175e  mov     ebp, eax
0x140051760  test    eax, eax
0x140051762  jnz     loc_140051680
0x140051768  mov     rdx, [rsp+78h+pBuffer]; SourceString
0x140051770  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140051775  call    cs:__imp_RtlInitUnicodeString
0x14005177c  nop     dword ptr [rax+rax+00h]
0x140051781  movzx   edx, [rsp+78h+DestinationString.Length]
0x140051786  mov     r9, [rsp+78h+DestinationString.Buffer]
0x14005178b  mov     r8d, edx
0x14005178e  shr     r8d, 1
0x140051791  mov     ecx, r12d
0x140051794  jz      short loc_1400517A5
0x140051796  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x14005179c  jz      short loc_1400517AE
0x14005179e  inc     ecx
0x1400517a0  cmp     ecx, r8d
0x1400517a3  jb      short loc_140051796
0x1400517a5  cmp     ecx, r8d
0x1400517a8  jnb     loc_140051680
0x1400517ae  test    r14, r14
0x1400517b1  jnz     short loc_1400517CF
0x1400517b3  movzx   eax, cx
0x1400517b6  mov     qword ptr [rsp+78h+var_58+8], r9
0x1400517bb  add     ax, ax
0x1400517be  lea     r14, [rsp+78h+var_58]
0x1400517c3  mov     word ptr [rsp+78h+var_58+2], ax
0x1400517c8  mov     word ptr [rsp+78h+var_58], ax
0x1400517cd  jmp     short loc_1400517D4
0x1400517cf  movzx   eax, word ptr [rsp+78h+var_58]
0x1400517d4  test    r15, r15
0x1400517d7  jnz     loc_1400516B6
0x1400517dd  sub     dx, ax
0x1400517e0  lea     r15, [rsp+78h+var_48]
0x1400517e5  sub     dx, 2
0x1400517e9  inc     rcx
0x1400517ec  mov     word ptr [rsp+78h+var_48+2], dx
0x1400517f1  mov     word ptr [rsp+78h+var_48], dx
0x1400517f6  lea     rcx, [r9+rcx*2]
0x1400517fa  mov     qword ptr [rsp+78h+var_48+8], rcx
0x1400517ff  jmp     loc_1400516B6
0x140051804  mov     ebp, 80000005h
0x140051809  jmp     short loc_140051810
0x14005180b  mov     ebp, 0C0000062h
0x140051810  mov     rcx, [rsp+78h+pBuffer]; pvContextBuffer
0x140051818  mov     r15, [rsp+78h+var_28]
0x14005181d  mov     r14, [rsp+78h+arg_18]
0x140051825  test    rcx, rcx
0x140051828  jz      short loc_140051836
0x14005182a  call    cs:__imp_FreeContextBuffer
0x140051831  nop     dword ptr [rax+rax+00h]
0x140051836  mov     rcx, [rsp+78h+UserInformation]; Buffer
0x14005183e  test    rcx, rcx
0x140051841  jz      short loc_14005184F
0x140051843  call    cs:__imp_LsaFreeReturnBuffer
0x14005184a  nop     dword ptr [rax+rax+00h]
0x14005184f  mov     eax, ebp
0x140051851  mov     rbp, [rsp+78h+arg_0]
0x140051859  add     rsp, 58h
0x14005185d  pop     r12
0x14005185f  pop     rdi
0x140051860  pop     rsi
0x140051861  pop     rbx
0x140051862  retn
0x140051864  mov     eax, 0C000000Dh
0x140051869  add     rsp, 58h
0x14005186d  pop     r12
0x14005186f  pop     rdi
0x140051870  pop     rsi
0x140051871  pop     rbx
0x140051872  retn
```
