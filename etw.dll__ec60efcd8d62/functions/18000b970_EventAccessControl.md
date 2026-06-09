# EventAccessControl

- ea: `0x18000b970`
- end: `0x18000bbda`
- name: `EventAccessControl`
- size: `618`
- prototype: `ULONG __stdcall(LPGUID Guid, ULONG Operation, PSID Sid, ULONG Rights, BOOLEAN AllowOrDeny)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001008`
- `0x180001560`
- `0x180002ec4`
- `0x180008808`
- `0x18000b970`
- `0x180013e28`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18000bb7f`
- `ntdll!RtlSetLastWin32Error` at `0x18000bb7f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b9fa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b9fa`

## pseudocode

```c
ULONG __stdcall EventAccessControl(LPGUID Guid, ULONG Operation, PSID Sid, ULONG Rights, BOOLEAN AllowOrDeny)
{
  __int16 *v9; // rcx
  GUID *v10; // rdx
  int v11; // eax
  DWORD v12; // ebx
  BOOLEAN v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v16; // [rsp+38h] [rbp-C8h] BYREF
  ULONG v17; // [rsp+3Ch] [rbp-C4h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v19; // [rsp+50h] [rbp-B0h]
  __int16 v20; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+5Ah] [rbp-A6h]
  __int16 v22; // [rsp+5Eh] [rbp-A2h]
  int v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+68h] [rbp-98h] BYREF
  char v25; // [rsp+6Ch] [rbp-94h]
  GUID ActivityId; // [rsp+70h] [rbp-90h] BYREF
  GUID v27; // [rsp+90h] [rbp-70h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[32]; // [rsp+B0h] [rbp-50h] BYREF
  GUID *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  ULONG *v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  __int16 *v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F8h] [rbp-8h]
  int v36; // [rsp+FCh] [rbp-4h]
  ULONG *v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  BOOLEAN *v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+118h] [rbp+18h]

  v20 = 257;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v15 = 0;
  v24 = 0;
  v25 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v24 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    v14 = AllowOrDeny;
    v9 = &v20;
    v16 = Rights;
    if ( Sid )
      v9 = (__int16 *)Sid;
    v17 = Operation;
    if ( Guid )
    {
      v10 = &v27;
      v27 = *Guid;
    }
    else
    {
      v10 = (GUID *)&v28;
      v28 = 0;
    }
    v40 = 1;
    v39 = &v14;
    v38 = 4;
    v37 = &v16;
    v11 = *((unsigned __int8 *)v9 + 1);
    v34 = v9;
    v30 = v10;
    v36 = 0;
    v33 = 4;
    v35 = 4 * v11 + 8;
    v32 = &v17;
    v31 = 16;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)word_18001903A,
      (__int64)&ActivityId,
      0,
      7,
      (__int64)v29);
  }
  v19 = 1;
  v18[0] = &v24;
  v18[1] = &v15;
  if ( Guid && Sid && Operation < 4 )
  {
    v12 = EtwpSetOrAddAce(Guid, Operation, Sid, Rights, AllowOrDeny);
    v15 = v12;
    if ( !v12 )
      goto LABEL_22;
  }
  else
  {
    v12 = 87;
    v15 = 87;
  }
  RtlSetLastWin32Error(v12);
  v12 = v15;
LABEL_22:
  if ( v19 )
    lambda_29bd5eda0039bb8a9fcac22374a1af1a_::operator()(v18);
  if ( v24 == 1 )
  {
    v24 = 2;
    _tlgWriteActivityAutoStop<16,5>((unsigned int *)&dword_18001D020, (__int64)&ActivityId);
  }
  return v12;
}

```

## disassembly

```asm
0x18000b970  push    rbp
0x18000b972  push    rbx
0x18000b973  push    rsi
0x18000b974  push    rdi
0x18000b975  push    r12
0x18000b977  push    r14
0x18000b979  push    r15
0x18000b97b  lea     rbp, [rsp-30h]
0x18000b980  sub     rsp, 130h
0x18000b987  mov     rax, cs:__security_cookie
0x18000b98e  xor     rax, rsp
0x18000b991  mov     [rbp+60h+var_40], rax
0x18000b995  xor     eax, eax
0x18000b997  mov     [rsp+160h+var_108], 101h
0x18000b99e  xor     r12d, r12d
0x18000b9a1  mov     [rsp+160h+var_106], eax
0x18000b9a5  mov     [rsp+160h+var_102], ax
0x18000b9aa  mov     r15d, r9d
0x18000b9ad  mov     [rsp+160h+var_100], eax
0x18000b9b1  mov     rdi, r8
0x18000b9b4  mov     eax, cs:dword_18001D020
0x18000b9ba  mov     esi, edx
0x18000b9bc  mov     [rsp+160h+var_12C], r12d
0x18000b9c1  mov     rbx, rcx
0x18000b9c4  mov     [rsp+160h+var_F8], r12d
0x18000b9c9  mov     [rsp+160h+var_F4], r12b
0x18000b9ce  cmp     eax, 5
0x18000b9d1  jbe     short loc_18000BA02
0x18000b9d3  mov     rcx, cs:qword_18001D038
0x18000b9da  mov     rax, cs:qword_18001D030
0x18000b9e1  test    al, 10h
0x18000b9e3  jz      short loc_18000BA02
0x18000b9e5  mov     rax, rcx
0x18000b9e8  and     eax, 10h
0x18000b9eb  cmp     rax, rcx
0x18000b9ee  jnz     short loc_18000BA02
0x18000b9f0  lea     rdx, [rsp+160h+ActivityId]; ActivityId
0x18000b9f5  lea     ecx, [r12+3]; ControlCode
0x18000b9fa  call    cs:__imp_EventActivityIdControl
0x18000ba00  jmp     short loc_18000BA0A
0x18000ba02  xorps   xmm0, xmm0
0x18000ba05  movups  xmmword ptr [rsp+160h+ActivityId.Data1], xmm0
0x18000ba0a  mov     eax, cs:dword_18001D020
0x18000ba10  mov     r14b, [rbp+60h+AllowOrDeny]
0x18000ba17  mov     [rsp+160h+var_F8], 1
0x18000ba1f  cmp     eax, 5
0x18000ba22  jbe     loc_18000BB2B
0x18000ba28  mov     rcx, cs:qword_18001D038
0x18000ba2f  mov     rax, cs:qword_18001D030
0x18000ba36  test    al, 10h
0x18000ba38  jz      loc_18000BB2B
0x18000ba3e  mov     rax, rcx
0x18000ba41  and     eax, 10h
0x18000ba44  cmp     rax, rcx
0x18000ba47  jnz     loc_18000BB2B
0x18000ba4d  test    rdi, rdi
0x18000ba50  mov     [rsp+160h+var_130], r14b
0x18000ba55  lea     rcx, [rsp+160h+var_108]
0x18000ba5a  mov     [rsp+160h+var_128], r15d
0x18000ba5f  cmovnz  rcx, rdi
0x18000ba63  mov     [rsp+160h+var_124], esi
0x18000ba67  test    rbx, rbx
0x18000ba6a  jz      short loc_18000BA7A
0x18000ba6c  movups  xmm0, xmmword ptr [rbx]
0x18000ba6f  lea     rdx, [rbp+60h+var_D0]
0x18000ba73  movdqu  [rbp+60h+var_D0], xmm0
0x18000ba78  jmp     short loc_18000BA85
0x18000ba7a  xorps   xmm0, xmm0
0x18000ba7d  lea     rdx, [rbp+60h+var_C0]
0x18000ba81  movups  [rbp+60h+var_C0], xmm0
0x18000ba85  cmp     [rsp+160h+var_F4], r12b
0x18000ba8a  jz      short loc_18000BAAA
0x18000ba8c  cmp     [rbp+60h+var_E0], r12d
0x18000ba90  jnz     short loc_18000BAA4
0x18000ba92  cmp     [rbp+60h+var_DC], r12d
0x18000ba96  jnz     short loc_18000BAA4
0x18000ba98  cmp     [rbp+60h+var_D8], r12d
0x18000ba9c  jnz     short loc_18000BAA4
0x18000ba9e  cmp     [rbp+60h+var_D4], r12d
0x18000baa2  jz      short loc_18000BAAA
0x18000baa4  lea     r9, [rbp+60h+var_E0]
0x18000baa8  jmp     short loc_18000BAAD
0x18000baaa  mov     r9, r12
0x18000baad  lea     rax, [rsp+160h+var_130]
0x18000bab2  mov     [rbp+60h+var_48], 1
0x18000baba  mov     [rbp+60h+var_50], rax
0x18000babe  lea     r8, [rsp+160h+ActivityId]
0x18000bac3  lea     rax, [rsp+160h+var_128]
0x18000bac8  mov     [rbp+60h+var_58], 4
0x18000bad0  mov     [rbp+60h+var_60], rax
0x18000bad4  movzx   eax, byte ptr [rcx+1]
0x18000bad8  mov     [rbp+60h+var_70], rcx
0x18000badc  lea     rcx, dword_18001D020
0x18000bae3  mov     [rbp+60h+var_90], rdx
0x18000bae7  lea     rdx, word_18001903A
0x18000baee  mov     [rbp+60h+var_64], r12d
0x18000baf2  lea     eax, ds:8[rax*4]
0x18000baf9  mov     [rbp+60h+var_78], 4
0x18000bb01  mov     [rbp+60h+var_68], eax
0x18000bb04  lea     rax, [rsp+160h+var_124]
0x18000bb09  mov     [rbp+60h+var_80], rax
0x18000bb0d  lea     rax, [rbp+60h+var_B0]
0x18000bb11  mov     [rsp+160h+var_138], rax
0x18000bb16  mov     dword ptr [rsp+160h+var_140], 7
0x18000bb1e  mov     [rbp+60h+var_88], 10h
0x18000bb26  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000bb2b  mov     [rsp+160h+var_110], 1
0x18000bb30  lea     rax, [rsp+160h+var_F8]
0x18000bb35  mov     [rsp+160h+var_120], rax
0x18000bb3a  lea     rax, [rsp+160h+var_12C]
0x18000bb3f  mov     [rsp+160h+var_118], rax
0x18000bb44  test    rbx, rbx
0x18000bb47  jz      short loc_18000BB74
0x18000bb49  test    rdi, rdi
0x18000bb4c  jz      short loc_18000BB74
0x18000bb4e  cmp     esi, 4
0x18000bb51  jnb     short loc_18000BB74
0x18000bb53  mov     r9d, r15d; unsigned int
0x18000bb56  mov     [rsp+160h+var_140], r14b; unsigned __int8
0x18000bb5b  mov     r8, rdi; void *
0x18000bb5e  mov     edx, esi; unsigned int
0x18000bb60  mov     rcx, rbx; struct _GUID *
0x18000bb63  call    ?EtwpSetOrAddAce@@YAKPEAU_GUID@@KPEAXKE@Z; EtwpSetOrAddAce(_GUID *,ulong,void *,ulong,uchar)
0x18000bb68  mov     ebx, eax
0x18000bb6a  mov     [rsp+160h+var_12C], eax
0x18000bb6e  test    eax, eax
0x18000bb70  jz      short loc_18000BB89
0x18000bb72  jmp     short loc_18000BB7D
0x18000bb74  mov     ebx, 57h ; 'W'
0x18000bb79  mov     [rsp+160h+var_12C], ebx
0x18000bb7d  mov     ecx, ebx; LastError
0x18000bb7f  call    cs:__imp_RtlSetLastWin32Error
0x18000bb85  mov     ebx, [rsp+160h+var_12C]
0x18000bb89  cmp     [rsp+160h+var_110], r12b
0x18000bb8e  jz      short loc_18000BB9A
0x18000bb90  lea     rcx, [rsp+160h+var_120]
0x18000bb95  call    _lambda_29bd5eda0039bb8a9fcac22374a1af1a___operator__
0x18000bb9a  cmp     [rsp+160h+var_F8], 1
0x18000bb9f  jnz     short loc_18000BBBA
0x18000bba1  lea     rdx, [rsp+160h+ActivityId]
0x18000bba6  mov     [rsp+160h+var_F8], 2
0x18000bbae  lea     rcx, dword_18001D020
0x18000bbb5  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000bbba  mov     eax, ebx
0x18000bbbc  mov     rcx, [rbp+60h+var_40]
0x18000bbc0  xor     rcx, rsp; StackCookie
0x18000bbc3  call    __security_check_cookie
0x18000bbc8  add     rsp, 130h
0x18000bbcf  pop     r15
0x18000bbd1  pop     r14
0x18000bbd3  pop     r12
0x18000bbd5  pop     rdi
0x18000bbd6  pop     rsi
0x18000bbd7  pop     rbx
0x18000bbd8  pop     rbp
0x18000bbd9  retn
```
