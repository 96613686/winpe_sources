# QuicConnRecvRetry

- ea: `0x140042e10`
- end: `0x1400430e8`
- name: `QuicConnRecvRetry`
- size: `728`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140015b70`

## callees

- `0x1400087bc`
- `0x140008ef0`
- `0x14001c664`
- `0x140021e20`
- `0x140026a88`
- `0x14002a55c`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ed00`
- `0x140041bb4`
- `0x140041de0`
- `0x140042e10`
- `0x140043368`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140042fb0`
- `ntoskrnl!ExAllocatePool2` at `0x140042fb0`

## string_xrefs

- `0x140042e4f`: `Already received server response`
- `0x140042e7e`: `No room for Retry Token`
- `0x140042fd4`: `InitialToken`
- `0x140042fe0`: `InitialToken alloc failed`
- `0x140043080`: `Failed to create initial keys`

## pseudocode

```c
__int64 __fastcall QuicConnRecvRetry(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  __int64 v3; // rsi
  const char *v4; // r8
  __int64 v5; // r10
  char *v6; // r14
  char *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int16 v11; // di
  const void *v12; // r15
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  void *Pool2; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 result; // rax
  __int64 v21; // r9
  __int64 v22; // rax
  int v23; // ecx
  int Initial; // eax
  __int64 v25; // [rsp+28h] [rbp-60h]
  _QWORD v26[2]; // [rsp+40h] [rbp-48h] BYREF

  v2 = a2;
  v3 = a1;
  if ( *(_DWORD *)a1 == 4 )
  {
    v4 = "Retry sent to server";
    return QuicPacketLogDrop(a1, a2, v4);
  }
  if ( *(char *)(a1 + 249) < 0 )
  {
    v4 = "Already received server response";
    return QuicPacketLogDrop(a1, a2, v4);
  }
  if ( (*(_BYTE *)(a1 + 248) & 0x30) != 0 )
  {
    v4 = "Retry while shutting down";
    return QuicPacketLogDrop(a1, a2, v4);
  }
  if ( *(unsigned __int16 *)(a2 + 80) - *(unsigned __int16 *)(a2 + 82) <= 16 )
  {
    v4 = "No room for Retry Token";
    return QuicPacketLogDrop(a1, a2, v4);
  }
  if ( !(unsigned __int8)QuicVersionNegotiationExtIsVersionClientSupported(
                           a1,
                           *(unsigned int *)(*(_QWORD *)(a2 + 56) + 1LL)) )
  {
    QuicPacketLogDrop(v3, v2, "Retry Version not supported by client");
    v5 = *(_QWORD *)(v2 + 56);
  }
  v6 = 0;
  v7 = QuicSupportedVersionList;
  v8 = 0;
  while ( *(_DWORD *)v7 != *(_DWORD *)(v5 + 1) )
  {
    v8 = (unsigned int)(v8 + 1);
    v7 += 88;
    if ( (unsigned int)v8 >= 4 )
      goto LABEL_15;
  }
  v6 = &QuicSupportedVersionList[88 * v8];
  if ( v6 )
    goto LABEL_16;
LABEL_15:
  CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 3579, "VersionInfo != ((void *)0)");
  __int2c();
LABEL_16:
  v9 = *(_QWORD *)(v2 + 56);
  v10 = *(unsigned __int16 *)(v2 + 82);
  v25 = v9;
  v11 = *(_WORD *)(v2 + 80) - v10 - 16;
  v12 = (const void *)(v9 + v10);
  LOBYTE(v9) = 1;
  QuicPacketLogHeader(v3, v9, 0, 0, *(_WORD *)(v2 + 80), v25, 0);
  v13 = *(_QWORD *)(v3 + 1288);
  v14 = v13 + 48;
  LOBYTE(v13) = *(_BYTE *)(v13 + 33);
  if ( (int)QuicPacketGenerateRetryIntegrity(
              v6,
              v13,
              v14,
              (unsigned __int16)(*(_WORD *)(v2 + 80) - 16),
              *(_QWORD *)(v2 + 56),
              v26) < 0 )
  {
    v4 = "Failed to generate integrity field";
LABEL_18:
    a2 = v2;
    a1 = v3;
    return QuicPacketLogDrop(a1, a2, v4);
  }
  v15 = *(unsigned __int16 *)(v2 + 80);
  v16 = *(_QWORD *)(v2 + 56);
  if ( v26[0] != *(_QWORD *)(v15 + v16 - 16) || v26[1] != *(_QWORD *)(v15 + v16 - 8) )
  {
    v4 = "Invalid integrity field";
    goto LABEL_18;
  }
  Pool2 = (void *)ExAllocatePool2(258, v11, 875782993);
  *(_QWORD *)(v3 + 3512) = Pool2;
  if ( !Pool2 )
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v19, v18, "InitialToken", v11);
    v4 = "InitialToken alloc failed";
    goto LABEL_18;
  }
  *(_WORD *)(v3 + 3520) = v11;
  memmove(Pool2, v12, v11);
  result = QuicConnUpdateDestCid(v3, v2);
  if ( (_BYTE)result )
  {
    *(_BYTE *)(v3 + 249) |= 0x80u;
    *(_BYTE *)(v3 + 250) |= 1u;
    QuicPacketKeyFree(*(PVOID *)(v3 + 2872));
    QuicPacketKeyFree(*(PVOID *)(v3 + 2920));
    v21 = *(_QWORD *)(v3 + 1288);
    *(_QWORD *)(v3 + 2872) = 0;
    *(_QWORD *)(v3 + 2920) = 0;
    v22 = v21 + 48;
    LOBYTE(v21) = *(_BYTE *)(v21 + 33);
    LOBYTE(v23) = *(_DWORD *)v3 == 4;
    Initial = QuicPacketKeyCreateInitial(v23, (int)v6 + 56, (int)v6 + 4, v21, v22, v3 + 2872, v3 + 2920);
    if ( Initial >= 0 )
    {
      *(_DWORD *)(v3 + 3632) |= 2u;
      result = QuicConnRestart(v3, 0);
      *(_BYTE *)(v2 + 93) |= 2u;
    }
    else
    {
      return QuicConnTryClose(v3, 18, Initial, (unsigned int)"Failed to create initial keys", 29);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140042e10  mov     [rsp+arg_10], rbx
0x140042e15  push    rbp
0x140042e16  push    rsi
0x140042e17  push    rdi
0x140042e18  push    r14
0x140042e1a  push    r15
0x140042e1c  sub     rsp, 60h
0x140042e20  mov     rax, cs:__security_cookie
0x140042e27  xor     rax, rsp
0x140042e2a  mov     [rsp+88h+var_38], rax
0x140042e2f  cmp     dword ptr [rcx], 4
0x140042e32  mov     rbp, rdx
0x140042e35  mov     rsi, rcx
0x140042e38  jnz     short loc_140042E46
0x140042e3a  lea     r8, aRetrySentToSer; "Retry sent to server"
0x140042e41  jmp     loc_1400430C1
0x140042e46  cmp     byte ptr [rcx+0F9h], 0
0x140042e4d  jge     short loc_140042E5B
0x140042e4f  lea     r8, aAlreadyReceive; "Already received server response"
0x140042e56  jmp     loc_1400430C1
0x140042e5b  test    byte ptr [rcx+0F8h], 30h
0x140042e62  jnz     loc_1400430BA
0x140042e68  movzx   ecx, word ptr [rdx+50h]
0x140042e6c  mov     ebx, 10h
0x140042e71  movzx   eax, word ptr [rdx+52h]
0x140042e75  sub     ecx, eax
0x140042e77  cmp     ecx, ebx
0x140042e79  mov     rcx, rsi
0x140042e7c  jg      short loc_140042E8A
0x140042e7e  lea     r8, aNoRoomForRetry; "No room for Retry Token"
0x140042e85  jmp     loc_1400430C1
0x140042e8a  mov     r10, [rdx+38h]
0x140042e8e  mov     edx, [r10+1]
0x140042e92  call    QuicVersionNegotiationExtIsVersionClientSupported
0x140042e97  test    al, al
0x140042e99  jnz     short loc_140042EB1
0x140042e9b  lea     r8, aRetryVersionNo; "Retry Version not supported by client"
0x140042ea2  mov     rdx, rbp
0x140042ea5  mov     rcx, rsi
0x140042ea8  call    QuicPacketLogDrop
0x140042ead  mov     r10, [rbp+38h]
0x140042eb1  mov     edx, [r10+1]
0x140042eb5  lea     r8, QuicSupportedVersionList
0x140042ebc  xor     r14d, r14d
0x140042ebf  mov     rcx, r8
0x140042ec2  xor     eax, eax
0x140042ec4  cmp     [rcx], edx
0x140042ec6  jz      short loc_140042ED5
0x140042ec8  inc     eax
0x140042eca  add     rcx, 58h ; 'X'
0x140042ece  cmp     eax, 4
0x140042ed1  jb      short loc_140042EC4
0x140042ed3  jmp     short loc_140042EDE
0x140042ed5  imul    r14, rax, 58h ; 'X'
0x140042ed9  add     r14, r8
0x140042edc  jnz     short loc_140042EF8
0x140042ede  lea     r8, aVersioninfoVoi; "VersionInfo != ((void *)0)"
0x140042ee5  mov     edx, 0DFBh
0x140042eea  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x140042ef1  call    CxPlatLogAssert
0x140042ef6  int     2Ch; Windows NT - assertion failure
0x140042ef8  mov     rdx, [rbp+38h]
0x140042efc  xor     r9d, r9d
0x140042eff  movzx   ecx, word ptr [rbp+50h]
0x140042f03  xor     r8d, r8d
0x140042f06  movzx   eax, word ptr [rbp+52h]
0x140042f0a  movzx   edi, cx
0x140042f0d  and     dword ptr [rsp+88h+var_58], 0
0x140042f12  sub     di, ax
0x140042f15  mov     [rsp+88h+var_60], rdx
0x140042f1a  sub     di, bx
0x140042f1d  mov     word ptr [rsp+88h+var_68], cx
0x140042f22  mov     rcx, rsi
0x140042f25  lea     r15, [rdx+rax]
0x140042f29  mov     dl, 1
0x140042f2b  call    QuicPacketLogHeader
0x140042f30  mov     rdx, [rsi+508h]
0x140042f37  lea     rax, [rsp+88h+var_48]
0x140042f3c  movzx   r9d, word ptr [rbp+50h]
0x140042f41  mov     rcx, r14
0x140042f44  mov     [rsp+88h+var_60], rax
0x140042f49  sub     r9w, bx
0x140042f4d  mov     rax, [rbp+38h]
0x140042f51  lea     r8, [rdx+30h]
0x140042f55  mov     [rsp+88h+var_68], rax
0x140042f5a  mov     dl, [rdx+21h]
0x140042f5d  call    QuicPacketGenerateRetryIntegrity
0x140042f62  test    eax, eax
0x140042f64  jns     short loc_140042F78
0x140042f66  lea     r8, aFailedToGenera; "Failed to generate integrity field"
0x140042f6d  mov     rdx, rbp
0x140042f70  mov     rcx, rsi
0x140042f73  jmp     loc_1400430C1
0x140042f78  movzx   ecx, word ptr [rbp+50h]
0x140042f7c  mov     rdx, [rbp+38h]
0x140042f80  mov     rax, [rsp+88h+var_48]
0x140042f85  cmp     rax, [rcx+rdx-10h]
0x140042f8a  jnz     loc_1400430AE
0x140042f90  mov     rax, [rsp+88h+var_40]
0x140042f95  cmp     rax, [rcx+rdx-8]
0x140042f9a  jnz     loc_1400430AE
0x140042fa0  movzx   ebx, di
0x140042fa3  mov     r8d, 34336351h
0x140042fa9  mov     edx, ebx
0x140042fab  mov     ecx, 102h
0x140042fb0  call    cs:__imp_ExAllocatePool2
0x140042fb7  nop     dword ptr [rax+rax+00h]
0x140042fbc  mov     [rsi+0DB8h], rax
0x140042fc3  test    rax, rax
0x140042fc6  jnz     short loc_140042FE9
0x140042fc8  test    cs:Microsoft_QuicEnableBits, 2
0x140042fcf  jz      short loc_140042FE0
0x140042fd1  mov     r9d, ebx
0x140042fd4  lea     r8, aInitialtoken; "InitialToken"
0x140042fdb  call    McTemplateU0sx_EtwWriteTransfer
0x140042fe0  lea     r8, aInitialtokenAl; "InitialToken alloc failed"
0x140042fe7  jmp     short loc_140042F6D
0x140042fe9  mov     r8, rbx; Size
0x140042fec  mov     [rsi+0DC0h], di
0x140042ff3  mov     rdx, r15; Src
0x140042ff6  mov     rcx, rax; void *
0x140042ff9  call    memmove
0x140042ffe  mov     rdx, rbp
0x140043001  mov     rcx, rsi
0x140043004  call    QuicConnUpdateDestCid
0x140043009  test    al, al
0x14004300b  jz      loc_1400430C6
0x140043011  or      byte ptr [rsi+0F9h], 80h
0x140043018  lea     rdi, [rsi+0B38h]
0x14004301f  or      byte ptr [rsi+0FAh], 1
0x140043026  mov     rcx, [rdi]; P
0x140043029  call    QuicPacketKeyFree
0x14004302e  lea     rbx, [rsi+0B68h]
0x140043035  mov     rcx, [rbx]; P
0x140043038  call    QuicPacketKeyFree
0x14004303d  mov     r9, [rsi+508h]
0x140043044  lea     r8, [r14+4]
0x140043048  and     qword ptr [rdi], 0
0x14004304c  lea     rdx, [r14+38h]
0x140043050  and     qword ptr [rbx], 0
0x140043054  cmp     dword ptr [rsi], 4
0x140043057  lea     rax, [r9+30h]
0x14004305b  mov     [rsp+88h+var_58], rbx
0x140043060  mov     r9b, [r9+21h]
0x140043064  setz    cl
0x140043067  mov     [rsp+88h+var_60], rdi
0x14004306c  mov     [rsp+88h+var_68], rax
0x140043071  call    QuicPacketKeyCreateInitial
0x140043076  mov     rcx, rsi
0x140043079  test    eax, eax
0x14004307b  jns     short loc_14004309A
0x14004307d  movsxd  r8, eax
0x140043080  lea     r9, aFailedToCreate; "Failed to create initial keys"
0x140043087  mov     edx, 12h
0x14004308c  mov     word ptr [rsp+88h+var_68], 1Dh
0x140043093  call    QuicConnTryClose
0x140043098  jmp     short loc_1400430C6
0x14004309a  or      dword ptr [rsi+0E30h], 2
0x1400430a1  xor     edx, edx
0x1400430a3  call    QuicConnRestart
0x1400430a8  or      byte ptr [rbp+5Dh], 2
0x1400430ac  jmp     short loc_1400430C6
0x1400430ae  lea     r8, aInvalidIntegri; "Invalid integrity field"
0x1400430b5  jmp     loc_140042F6D
0x1400430ba  lea     r8, aRetryWhileShut; "Retry while shutting down"
0x1400430c1  call    QuicPacketLogDrop
0x1400430c6  mov     rcx, [rsp+88h+var_38]
0x1400430cb  xor     rcx, rsp; StackCookie
0x1400430ce  call    __security_check_cookie
0x1400430d3  mov     rbx, [rsp+88h+arg_10]
0x1400430db  add     rsp, 60h
0x1400430df  pop     r15
0x1400430e1  pop     r14
0x1400430e3  pop     rdi
0x1400430e4  pop     rsi
0x1400430e5  pop     rbp
0x1400430e6  retn
```
