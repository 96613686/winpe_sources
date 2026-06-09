# CCtfServerPort::RemoveClient(CCtfServerPort::ClientInfo * &)

- ea: `0x1800429e8`
- end: `0x180042cd5`
- name: `?RemoveClient@CCtfServerPort@@AEAA_NAEAPEAUClientInfo@1@@Z`
- size: `749`
- prototype: `bool __fastcall(CCtfServerPort *__hidden this, struct CCtfServerPort::ClientInfo **)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18004004c`
- `0x180040760`
- `0x180042cdc`
- `0x1800432a0`

## callees

- `0x1800139a4`
- `0x1800429e8`
- `0x18004366c`
- `0x180043760`
- `0x180043cbc`
- `0x18006a430`
- `0x1800771fc`
- `0x18009ead2`
- `0x1800b4768`
- `0x18010a010`

## import_xrefs

- `ntdll!NtClose` at `0x180042b1d`
- `ntdll!NtClose` at `0x180042b1d`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180042ad8`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180042ad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a60`
- `USER32!PostThreadMessageW` at `0x180042cbe`
- `USER32!PostThreadMessageW` at `0x180042cbe`

## pseudocode

```c
char __fastcall CCtfServerPort::RemoveClient(CCtfServerPort *this, struct CCtfServerPort::ClientInfo **a2)
{
  int v4; // ecx
  unsigned __int64 v5; // rdx
  int v6; // r8d
  int v7; // edi
  __int64 v8; // r9
  unsigned int v9; // eax
  int v10; // r14d
  unsigned __int64 v11; // r14
  void *v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // edi
  unsigned __int64 v16; // rax
  HLOCAL v17; // rax
  void *v18; // rcx
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  unsigned __int64 v22; // r14
  char *v23; // rdx
  char *v24; // r8
  _QWORD *v25; // rdi
  unsigned int v26; // edx
  CCtfServerPort::ClientInfo *v27; // rcx
  unsigned int v28; // ecx
  void **v29; // [rsp+20h] [rbp-38h] BYREF
  __int128 v30; // [rsp+28h] [rbp-30h]
  int v31; // [rsp+38h] [rbp-20h]
  char v32; // [rsp+3Ch] [rbp-1Ch]
  __int64 v33; // [rsp+40h] [rbp-18h]
  int v34; // [rsp+48h] [rbp-10h]
  struct MsgBase *v35; // [rsp+A0h] [rbp+48h] BYREF

  v4 = 0;
  v5 = (unsigned __int64)*a2;
  v6 = *((_DWORD *)this + 14);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v4 >= v6 )
        return 0;
      v7 = (v6 + v4) >> 1;
      v8 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v7);
      v9 = *(_DWORD *)(v8 + 20);
      if ( v9 <= *(_DWORD *)(v5 + 20) )
        break;
      v6 = (v6 + v4) >> 1;
    }
    if ( v9 >= *(_DWORD *)(v5 + 20) )
      break;
    v4 = v7 + 1;
  }
  if ( v8 != v5 )
    return 0;
  v10 = 0;
  if ( *(int *)(v5 + 72) > 0 )
  {
    do
      cicMemFree(*(_QWORD *)(*((_QWORD *)*a2 + 8) + 8LL * v10++));
    while ( v10 < *((_DWORD *)*a2 + 18) );
  }
  v11 = (unsigned __int64)*a2;
  v12 = (void *)*((_QWORD *)*a2 + 8);
  if ( v12 )
    LocalFree(v12);
  *(_QWORD *)(v11 + 64) = 0;
  *(_QWORD *)(v11 + 72) = 0;
  if ( v7 >= 0 )
  {
    v13 = v7 + 1;
    if ( v7 + 1 >= 0 && v13 <= *((_DWORD *)this + 14) )
    {
      if ( v13 < *((_DWORD *)this + 14) )
        memmove_0(
          (void *)(*((_QWORD *)this + 6) + 8LL * v7),
          (const void *)(*((_QWORD *)this + 6) + 8LL * v13),
          8LL * (*((_DWORD *)this + 14) + ~v7));
      v14 = *((_DWORD *)this + 15);
      --*((_DWORD *)this + 14);
      v5 = (unsigned int)(v14 >> 31);
      LODWORD(v5) = v14 % 2;
      v15 = v14 / 2;
      if ( v14 / 2 > *((_DWORD *)this + 14) && v15 != *((_DWORD *)this + 15) && v15 >= 0 )
      {
        v16 = 8LL * (unsigned int)v15;
        if ( v16 <= 0xFFFFFFFF )
        {
          v17 = LocalReAlloc(*((HLOCAL *)this + 6), (unsigned int)v16, 0x42u);
          if ( v17 )
          {
            *((_QWORD *)this + 6) = v17;
            *((_DWORD *)this + 15) = v15;
          }
        }
      }
    }
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*a2 + 8LL))(*a2, v5) )
  {
    v22 = (unsigned __int64)*a2;
    v23 = (char *)*a2 + 88;
    v24 = (char *)*a2 + 96;
    if ( *(_QWORD *)v23 )
      *(_QWORD *)(*(_QWORD *)v23 + 96LL) = *(_QWORD *)v24;
    v25 = (_QWORD *)((char *)this + 112);
    if ( *(_QWORD *)v24 )
    {
      *(_QWORD *)(*(_QWORD *)v24 + 88LL) = *(_QWORD *)v23;
    }
    else if ( (char *)((*v25 + 88LL) & -(__int64)(*v25 != 0)) == v23 )
    {
      *v25 = *(_QWORD *)v23;
    }
    *(_QWORD *)v23 = 0;
    *(_QWORD *)v24 = 0;
    CCtfServerPort::RemoveReferencesFromDeadServer(this, (struct CCtfServerPort::ImeServerInfo *)v22);
    if ( *(_DWORD *)(v22 + 128) )
    {
      v27 = (CCtfServerPort::ClientInfo *)*((_QWORD *)this + 16);
      v35 = 0;
      if ( v27 && CCtfServerPort::ClientInfo::FindCachedMessage(v27, v26, &v35) )
      {
        v29 = &CMsgThreadActiveProfiles::`vftable';
        v31 = 0;
        v30 = 0;
        v32 = 1;
        v33 = 0;
        v34 = 0;
        if ( (int)CMsgThreadActiveProfiles::Read((CMsgThreadActiveProfiles *)&v29, v35) >= 0 )
        {
          LODWORD(v35) = 0;
          if ( CCtfServerPort::ImeServerInfo::FindActiveProfile(
                 (CCtfServerPort::ImeServerInfo *)v22,
                 (const struct CMsgThreadActiveProfiles *)&v29,
                 (unsigned int *)&v35) )
          {
            CCtfServerPort::ClientInfo::PostMessageW(
              *((CCtfServerPort::ClientInfo **)this + 16),
              g_msgPrivate,
              0xDu,
              (unsigned int)v35);
          }
        }
        CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles((CMsgThreadActiveProfiles *)&v29);
      }
      if ( !*v25 )
        *((_BYTE *)this + 120) = 1;
      if ( *((_QWORD *)this + 12) )
      {
        if ( *(_DWORD *)(v22 + 128) )
          v28 = **(_DWORD **)(v22 + 120);
        else
          v28 = 0;
        PostThreadMessageW(*((_DWORD *)this + 26), g_msgPrivate, 0xAu, v28);
      }
    }
  }
  else if ( *((struct CCtfServerPort::ClientInfo **)this + 16) == *a2 )
  {
    *((_QWORD *)this + 16) = 0;
  }
  v18 = (void *)*((_QWORD *)*a2 + 1);
  if ( v18 )
  {
    *((_QWORD *)*a2 + 1) = 0;
    NtClose(v18);
  }
  v19 = (void (__fastcall ***)(_QWORD, __int64))*a2;
  if ( (*((_DWORD *)*a2 + 20))-- == 1 )
    (**v19)(v19, 1);
  *a2 = 0;
  return 1;
}

```

## disassembly

```asm
0x1800429e8  push    rbp
0x1800429ea  push    rbx
0x1800429eb  push    rsi
0x1800429ec  push    rdi
0x1800429ed  push    r12
0x1800429ef  push    r13
0x1800429f1  push    r14
0x1800429f3  push    r15
0x1800429f5  mov     rbp, rsp
0x1800429f8  sub     rsp, 58h
0x1800429fc  mov     rbx, rcx
0x1800429ff  xor     r12d, r12d
0x180042a02  mov     rsi, rdx
0x180042a05  mov     ecx, r12d
0x180042a08  mov     rdx, [rdx]
0x180042a0b  mov     r8d, [rbx+38h]
0x180042a0f  cmp     ecx, r8d
0x180042a12  jge     loc_180042B52
0x180042a18  mov     rax, [rbx+30h]
0x180042a1c  lea     edi, [r8+rcx]
0x180042a20  sar     edi, 1
0x180042a22  movsxd  r15, edi
0x180042a25  mov     r9, [rax+r15*8]
0x180042a29  mov     eax, [r9+14h]
0x180042a2d  cmp     eax, [rdx+14h]
0x180042a30  ja      short loc_180042A39
0x180042a32  jnb     short loc_180042A3E
0x180042a34  lea     ecx, [rdi+1]
0x180042a37  jmp     short loc_180042A0F
0x180042a39  mov     r8d, edi
0x180042a3c  jmp     short loc_180042A0F
0x180042a3e  cmp     r9, rdx
0x180042a41  jnz     loc_180042B52
0x180042a47  mov     r14d, r12d
0x180042a4a  cmp     [rdx+48h], r12d
0x180042a4e  jg      loc_180042B56
0x180042a54  mov     r14, [rsi]
0x180042a57  mov     rcx, [r14+40h]; hMem
0x180042a5b  test    rcx, rcx
0x180042a5e  jz      short loc_180042A66
0x180042a60  call    cs:__imp_LocalFree
0x180042a66  mov     [r14+40h], r12
0x180042a6a  mov     r13d, 0FFFFFFFFh
0x180042a70  mov     [r14+48h], r12
0x180042a74  test    edi, edi
0x180042a76  js      short loc_180042AEA
0x180042a78  lea     eax, [rdi+1]
0x180042a7b  test    eax, eax
0x180042a7d  js      short loc_180042AEA
0x180042a7f  cmp     eax, [rbx+38h]
0x180042a82  jg      short loc_180042AEA
0x180042a84  jge     short loc_180042AA5
0x180042a86  mov     rcx, [rbx+30h]
0x180042a8a  not     edi
0x180042a8c  add     edi, [rbx+38h]
0x180042a8f  cdqe
0x180042a91  movsxd  r8, edi
0x180042a94  shl     r8, 3; Size
0x180042a98  lea     rdx, [rcx+rax*8]; Src
0x180042a9c  lea     rcx, [rcx+r15*8]; void *
0x180042aa0  call    memmove_0
0x180042aa5  mov     eax, [rbx+3Ch]
0x180042aa8  mov     ecx, 2
0x180042aad  dec     dword ptr [rbx+38h]
0x180042ab0  cdq
0x180042ab1  idiv    ecx
0x180042ab3  mov     edi, eax
0x180042ab5  cmp     eax, [rbx+38h]
0x180042ab8  jle     short loc_180042AEA
0x180042aba  cmp     edi, [rbx+3Ch]
0x180042abd  jz      short loc_180042AEA
0x180042abf  test    edi, edi
0x180042ac1  js      short loc_180042AEA
0x180042ac3  mov     eax, edi
0x180042ac5  shl     rax, 3
0x180042ac9  cmp     rax, r13
0x180042acc  ja      short loc_180042AEA
0x180042ace  lea     r8d, [rcx+40h]; uFlags
0x180042ad2  mov     edx, eax; uBytes
0x180042ad4  mov     rcx, [rbx+30h]; hMem
0x180042ad8  call    cs:__imp_LocalReAlloc
0x180042ade  test    rax, rax
0x180042ae1  jz      short loc_180042AEA
0x180042ae3  mov     [rbx+30h], rax
0x180042ae7  mov     [rbx+3Ch], edi
0x180042aea  mov     rcx, [rsi]
0x180042aed  mov     rax, [rcx]
0x180042af0  mov     rax, [rax+8]
0x180042af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042af9  test    al, al
0x180042afb  jnz     short loc_180042B7B
0x180042afd  mov     rax, [rsi]
0x180042b00  cmp     [rbx+80h], rax
0x180042b07  jz      loc_180042CC9
0x180042b0d  mov     rax, [rsi]
0x180042b10  mov     rcx, [rax+8]; Handle
0x180042b14  test    rcx, rcx
0x180042b17  jz      short loc_180042B23
0x180042b19  mov     [rax+8], r12
0x180042b1d  call    cs:__imp_NtClose
0x180042b23  mov     rcx, [rsi]
0x180042b26  add     [rcx+50h], r13d
0x180042b2a  jnz     short loc_180042B3C
0x180042b2c  mov     rdx, [rcx]
0x180042b2f  mov     rax, [rdx]
0x180042b32  mov     edx, 1
0x180042b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b3c  mov     [rsi], r12
0x180042b3f  mov     al, 1
0x180042b41  add     rsp, 58h
0x180042b45  pop     r15
0x180042b47  pop     r14
0x180042b49  pop     r13
0x180042b4b  pop     r12
0x180042b4d  pop     rdi
0x180042b4e  pop     rsi
0x180042b4f  pop     rbx
0x180042b50  pop     rbp
0x180042b51  retn
0x180042b52  xor     al, al
0x180042b54  jmp     short loc_180042B41
0x180042b56  mov     rax, [rsi]
0x180042b59  movsxd  rdx, r14d
0x180042b5c  mov     rcx, [rax+40h]
0x180042b60  mov     rcx, [rcx+rdx*8]
0x180042b64  call    cicMemFree
0x180042b69  mov     rax, [rsi]
0x180042b6c  inc     r14d
0x180042b6f  cmp     r14d, [rax+48h]
0x180042b73  jge     loc_180042A54
0x180042b79  jmp     short loc_180042B56
0x180042b7b  mov     r14, [rsi]
0x180042b7e  lea     rdx, [r14+58h]
0x180042b82  mov     rcx, [rdx]
0x180042b85  lea     r8, [rdx+8]
0x180042b89  test    rcx, rcx
0x180042b8c  jnz     loc_180042C79
0x180042b92  mov     rcx, [r8]
0x180042b95  lea     rdi, [rbx+70h]
0x180042b99  test    rcx, rcx
0x180042b9c  jz      loc_180042C85
0x180042ba2  mov     rax, [rdx]
0x180042ba5  mov     [rcx+58h], rax
0x180042ba9  mov     [rdx], r12
0x180042bac  mov     rcx, rbx; this
0x180042baf  mov     rdx, r14; struct CCtfServerPort::ImeServerInfo *
0x180042bb2  mov     [r8], r12
0x180042bb5  call    ?RemoveReferencesFromDeadServer@CCtfServerPort@@AEAAXPEAUImeServerInfo@1@@Z; CCtfServerPort::RemoveReferencesFromDeadServer(CCtfServerPort::ImeServerInfo *)
0x180042bba  cmp     [r14+80h], r12d
0x180042bc1  jz      loc_180042B0D
0x180042bc7  mov     rcx, [rbx+80h]; this
0x180042bce  mov     [rbp+arg_0], r12
0x180042bd2  test    rcx, rcx
0x180042bd5  jz      short loc_180042C55
0x180042bd7  lea     r8, [rbp+arg_0]; struct MsgBase **
0x180042bdb  call    ?FindCachedMessage@ClientInfo@CCtfServerPort@@QEAA_NKPEAPEAUMsgBase@@@Z; CCtfServerPort::ClientInfo::FindCachedMessage(ulong,MsgBase * *)
0x180042be0  test    al, al
0x180042be2  jz      short loc_180042C55
0x180042be4  mov     rdx, [rbp+arg_0]; struct MsgBase *
0x180042be8  lea     rax, ??_7CMsgThreadActiveProfiles@@6B@; const CMsgThreadActiveProfiles::`vftable'
0x180042bef  xorps   xmm0, xmm0
0x180042bf2  mov     [rbp+var_38], rax
0x180042bf6  lea     rcx, [rbp+var_38]; this
0x180042bfa  mov     [rbp+var_20], r12d
0x180042bfe  movdqu  [rbp+var_30], xmm0
0x180042c03  mov     [rbp+var_1C], 1
0x180042c07  mov     [rbp+var_18], r12
0x180042c0b  mov     [rbp+var_10], r12d
0x180042c0f  call    ?Read@CMsgThreadActiveProfiles@@UEAAJPEAUMsgBase@@@Z; CMsgThreadActiveProfiles::Read(MsgBase *)
0x180042c14  test    eax, eax
0x180042c16  js      short loc_180042C4C
0x180042c18  lea     r8, [rbp+arg_0]; unsigned int *
0x180042c1c  mov     dword ptr [rbp+arg_0], r12d
0x180042c20  lea     rdx, [rbp+var_38]; struct CMsgThreadActiveProfiles *
0x180042c24  mov     rcx, r14; this
0x180042c27  call    ?FindActiveProfile@ImeServerInfo@CCtfServerPort@@QEAA_NPEBVCMsgThreadActiveProfiles@@PEAK@Z; CCtfServerPort::ImeServerInfo::FindActiveProfile(CMsgThreadActiveProfiles const *,ulong *)
0x180042c2c  test    al, al
0x180042c2e  jz      short loc_180042C4C
0x180042c30  mov     r9d, dword ptr [rbp+arg_0]; __int64
0x180042c34  mov     r8d, 0Dh; unsigned __int64
0x180042c3a  mov     edx, cs:?g_msgPrivate@@3IA; unsigned int
0x180042c40  mov     rcx, [rbx+80h]; this
0x180042c47  call    ?PostMessageW@ClientInfo@CCtfServerPort@@QEAA_NI_K_J@Z; CCtfServerPort::ClientInfo::PostMessageW(uint,unsigned __int64,__int64)
0x180042c4c  lea     rcx, [rbp+var_38]; this
0x180042c50  call    ??1CMsgThreadActiveProfiles@@UEAA@XZ; CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles(void)
0x180042c55  cmp     [rdi], r12
0x180042c58  jnz     short loc_180042C5E
0x180042c5a  mov     byte ptr [rbx+78h], 1
0x180042c5e  cmp     [rbx+60h], r12
0x180042c62  jz      loc_180042B0D
0x180042c68  cmp     [r14+80h], r12d
0x180042c6f  jz      short loc_180042CA9
0x180042c71  mov     rax, [r14+78h]
0x180042c75  mov     ecx, [rax]
0x180042c77  jmp     short loc_180042CAC
0x180042c79  mov     rax, [r8]
0x180042c7c  mov     [rcx+60h], rax
0x180042c80  jmp     loc_180042B92
0x180042c85  mov     rax, [rdi]
0x180042c88  lea     rcx, [rax+58h]
0x180042c8c  neg     rax
0x180042c8f  sbb     rax, rax
0x180042c92  and     rax, rcx
0x180042c95  cmp     rax, rdx
0x180042c98  jnz     loc_180042BA9
0x180042c9e  mov     rax, [rdx]
0x180042ca1  mov     [rdi], rax
0x180042ca4  jmp     loc_180042BA9
0x180042ca9  mov     ecx, r12d
0x180042cac  mov     edx, cs:?g_msgPrivate@@3IA; Msg
0x180042cb2  mov     r8d, 0Ah; wParam
0x180042cb8  mov     r9d, ecx; lParam
0x180042cbb  mov     ecx, [rbx+68h]; idThread
0x180042cbe  call    cs:__imp_PostThreadMessageW
0x180042cc4  jmp     loc_180042B0D
0x180042cc9  mov     [rbx+80h], r12
0x180042cd0  jmp     loc_180042B0D
```
