# CWebDriverDispatcher::HandleHandshakeMessage(ulong)

- ea: `0x180067b74`
- end: `0x180067d00`
- name: `?HandleHandshakeMessage@CWebDriverDispatcher@@AEAAXK@Z`
- size: `396`
- prototype: `void __fastcall(CWebDriverDispatcher *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180067d10`

## callees

- `0x18002b530`
- `0x180067b74`

## import_xrefs

- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x180067bd5`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x180067bd5`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180067cd6`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x180067cd6`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180067c60`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180067c60`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180067bc4`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180067bc4`
- `edgeIso!__imp_?IsoPostMessageUsingDataInBuffer@@YAJK_N@Z` at `0x180067cc8`
- `edgeIso!__imp_?IsoPostMessageUsingDataInBuffer@@YAJK_N@Z` at `0x180067cc8`
- `edgeIso!__imp_?IsoSaveProcessHandle@@YAJKPEAXPEAUIsoScope@@@Z` at `0x180067c31`
- `edgeIso!__imp_?IsoSaveProcessHandle@@YAJKPEAXPEAUIsoScope@@@Z` at `0x180067c31`
- `edgeIso!__imp_?IsoGetComponentData@@YAJKPEAU_IsoComponentCopy@@@Z` at `0x180067c18`
- `edgeIso!__imp_?IsoGetComponentData@@YAJKPEAU_IsoComponentCopy@@@Z` at `0x180067c18`
- `edgeIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180067c48`
- `edgeIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180067c6a`
- `edgeIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180067c48`
- `edgeIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x180067c6a`

## pseudocode

```c
void __fastcall CWebDriverDispatcher::HandleHandshakeMessage(CWebDriverDispatcher *this, unsigned int a2)
{
  GUID *v4; // rax
  GUID *v5; // rbx
  unsigned int AuthorityManager; // eax
  GUID *v7; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v8; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[12]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v10; // [rsp+4Ch] [rbp-B4h]
  unsigned int v11; // [rsp+50h] [rbp-B0h]
  __int64 v12; // [rsp+150h] [rbp+50h]
  __int64 v13; // [rsp+170h] [rbp+70h]

  v7 = 0;
  if ( (int)IsoGetMessageBufferAddress(a2, 1, 0, (struct _IsoMessage **)&v7, 0) < 0
    || VerifyUntrusted_IsoMessage_ExactSize(a2, 0x48u) )
  {
    v4 = v7;
  }
  else
  {
    v4 = 0;
    v7 = 0;
  }
  if ( v4 )
    v5 = v4 + 2;
  else
    v5 = 0;
  *((_DWORD *)this + 6) = *(_DWORD *)&v5->Data2;
  v12 = 0;
  v13 = 0;
  if ( (int)IsoGetComponentData(*(_DWORD *)&v5->Data2, (struct _IsoComponentCopy *)v9) >= 0 )
  {
    IsoSaveProcessHandle(v11, *(void **)&v5[2].Data1, 0);
    v8 = 0;
    v7 = 0;
    AuthorityManager = IsoGetAuthorityManager();
    if ( (int)IsoAllocMessageBuffer(AuthorityManager, &v8, 0x28u, (struct _IsoMessage **)&v7) >= 0 )
    {
      v7->Data1 = IsoGetAuthorityManager();
      *(_DWORD *)&v7->Data2 = *((_DWORD *)this + 7);
      *(_DWORD *)v7->Data4 = 0;
      *(_DWORD *)&v7->Data4[4] = 5;
      v7[1] = GUID_NULL;
      v7[2].Data1 = v10;
      *(_DWORD *)&v7[2].Data2 = *((_DWORD *)this + 6);
      if ( (int)IsoPostMessageUsingDataInBuffer(v8, 0) < 0 )
        IsoRemoveArtifact(v8);
    }
  }
}

```

## disassembly

```asm
0x180067b74  mov     [rsp-8+arg_10], rbx
0x180067b79  mov     [rsp-8+arg_18], rdi
0x180067b7e  push    rbp
0x180067b7f  lea     rbp, [rsp-90h]
0x180067b87  sub     rsp, 190h
0x180067b8e  mov     rax, cs:__security_cookie
0x180067b95  xor     rax, rsp
0x180067b98  mov     [rbp+90h+var_10], rax
0x180067b9f  mov     ebx, edx
0x180067ba1  mov     [rsp+190h+var_160], 0
0x180067baa  xor     r8d, r8d
0x180067bad  mov     [rsp+190h+var_170], 0
0x180067bb6  mov     rdi, rcx
0x180067bb9  lea     r9, [rsp+190h+var_160]
0x180067bbe  mov     ecx, ebx
0x180067bc0  lea     edx, [r8+1]
0x180067bc4  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x180067bca  test    eax, eax
0x180067bcc  js      short loc_180067BE8
0x180067bce  mov     edx, 48h ; 'H'
0x180067bd3  mov     ecx, ebx
0x180067bd5  call    cs:__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ExactSize(ulong,ulong)
0x180067bdb  test    al, al
0x180067bdd  jnz     short loc_180067BE8
0x180067bdf  xor     eax, eax
0x180067be1  mov     [rsp+190h+var_160], rax
0x180067be6  jmp     short loc_180067BED
0x180067be8  mov     rax, [rsp+190h+var_160]
0x180067bed  test    rax, rax
0x180067bf0  jz      short loc_180067BF8
0x180067bf2  lea     rbx, [rax+20h]
0x180067bf6  jmp     short loc_180067BFA
0x180067bf8  xor     ebx, ebx
0x180067bfa  mov     eax, [rbx+4]
0x180067bfd  lea     rdx, [rsp+190h+var_150]
0x180067c02  mov     [rdi+18h], eax
0x180067c05  mov     [rbp+90h+var_40], 0
0x180067c0d  mov     [rbp+90h+var_20], 0
0x180067c15  mov     ecx, [rbx+4]
0x180067c18  call    cs:__imp_?IsoGetComponentData@@YAJKPEAU_IsoComponentCopy@@@Z; IsoGetComponentData(ulong,_IsoComponentCopy *)
0x180067c1e  test    eax, eax
0x180067c20  js      loc_180067CDC
0x180067c26  mov     rdx, [rbx+20h]
0x180067c2a  xor     r8d, r8d
0x180067c2d  mov     ecx, [rsp+190h+var_140]
0x180067c31  call    cs:__imp_?IsoSaveProcessHandle@@YAJKPEAXPEAUIsoScope@@@Z; IsoSaveProcessHandle(ulong,void *,IsoScope *)
0x180067c37  mov     [rsp+190h+var_158], 0
0x180067c3f  mov     [rsp+190h+var_160], 0
0x180067c48  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x180067c4e  lea     r9, [rsp+190h+var_160]
0x180067c53  mov     r8d, 28h ; '('
0x180067c59  mov     ecx, eax
0x180067c5b  lea     rdx, [rsp+190h+var_158]
0x180067c60  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x180067c66  test    eax, eax
0x180067c68  js      short loc_180067CDC
0x180067c6a  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x180067c70  mov     rcx, [rsp+190h+var_160]
0x180067c75  xor     edx, edx
0x180067c77  mov     [rcx], eax
0x180067c79  mov     rax, [rsp+190h+var_160]
0x180067c7e  mov     ecx, [rdi+1Ch]
0x180067c81  mov     [rax+4], ecx
0x180067c84  mov     rax, [rsp+190h+var_160]
0x180067c89  mov     dword ptr [rax+8], 0
0x180067c90  mov     rax, [rsp+190h+var_160]
0x180067c95  mov     dword ptr [rax+0Ch], 5
0x180067c9c  mov     rax, [rsp+190h+var_160]
0x180067ca1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180067ca8  movdqu  xmmword ptr [rax+10h], xmm0
0x180067cad  mov     rcx, [rsp+190h+var_160]
0x180067cb2  mov     eax, [rsp+190h+var_144]
0x180067cb6  mov     [rcx+20h], eax
0x180067cb9  mov     ecx, [rdi+18h]
0x180067cbc  mov     rax, [rsp+190h+var_160]
0x180067cc1  mov     [rax+24h], ecx
0x180067cc4  mov     ecx, [rsp+190h+var_158]
0x180067cc8  call    cs:__imp_?IsoPostMessageUsingDataInBuffer@@YAJK_N@Z; IsoPostMessageUsingDataInBuffer(ulong,bool)
0x180067cce  test    eax, eax
0x180067cd0  jns     short loc_180067CDC
0x180067cd2  mov     ecx, [rsp+190h+var_158]
0x180067cd6  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x180067cdc  mov     rcx, [rbp+90h+var_10]
0x180067ce3  xor     rcx, rsp; StackCookie
0x180067ce6  call    __security_check_cookie
0x180067ceb  lea     r11, [rsp+190h+var_s0]
0x180067cf3  mov     rbx, [r11+20h]
0x180067cf7  mov     rdi, [r11+28h]
0x180067cfb  mov     rsp, r11
0x180067cfe  pop     rbp
0x180067cff  retn
```
