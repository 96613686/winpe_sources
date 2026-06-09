# EapLm::RasAuthAttributes::operator=(EapHost::Attributes const &)

- ea: `0x180029b80`
- end: `0x180029cd0`
- name: `??4RasAuthAttributes@EapLm@@QEAAAEAV01@AEBVAttributes@EapHost@@@Z`
- size: `336`
- prototype: `EapLm::RasAuthAttributes *__fastcall(EapLm::RasAuthAttributes *, const struct _EAP_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180023250`
- `0x180025340`

## callees

- `0x18000ec84`
- `0x180012a00`
- `0x180015534`
- `0x180015b00`
- `0x180015c30`
- `0x180029b80`
- `0x180029f14`
- `0x180029f40`
- `0x18002a104`
- `0x18002a190`
- `0x18002a20c`

## string_xrefs

- `0x180029bd1`: `RasAuthAttributeCreate`

## pseudocode

```c
EapLm::RasAuthAttributes *__fastcall EapLm::RasAuthAttributes::operator=(
        EapLm::RasAuthAttributes *a1,
        const struct _EAP_ATTRIBUTES *a2)
{
  unsigned __int64 v3; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v4; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v5; // rsi
  int v6; // ebp
  EapLm *v7; // rdi
  _DWORD *v8; // r14
  _BYTE *v9; // rcx
  unsigned __int8 *v10; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v11; // r8
  enum _RAS_AUTH_ATTRIBUTE_TYPE_ v12; // r9d
  int v13; // r10d
  unsigned int v14; // eax
  void *v16[2]; // [rsp+30h] [rbp-58h] BYREF
  EapLm *v17; // [rsp+40h] [rbp-48h]
  __int128 v18; // [rsp+48h] [rbp-40h]

  if ( !a2->dwNumberOfAttributes )
  {
    EapLm::RasAuthAttributes::Destroy(a1);
    return a1;
  }
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  EapHost::AutoAttributes::Assign((EapHost::AutoAttributes *)v16, a2);
  v5 = EapLm::RasAuthAttributeCreate(v17, v3);
  if ( !v5 )
    LowMemoryError::Throw(L"RasAuthAttributeCreate");
  v6 = 0;
  v7 = 0;
  v8 = v16[0];
  v9 = WPP_GLOBAL_Control;
  while ( v7 < v17 )
  {
    if ( v8[4 * (_QWORD)v7 + 1] && (v4 = *(struct _RAS_AUTH_ATTRIBUTE **)&v8[4 * (_QWORD)v7 + 2]) != 0 )
    {
      if ( EapLm::IsPointerValue((EapLm *)(unsigned int)v8[4 * (_QWORD)v7], (enum _RAS_AUTH_ATTRIBUTE_TYPE_)v4) )
        v14 = EapLm::RasAuthAttributeInsert(v7, (unsigned __int64)v5, v11, v12, v13, (unsigned int)v10, v16[0]);
      else
        v14 = EapLm::RasAuthAttributeInsert(v7, (unsigned __int64)v5, v11, v12, v13, *v10, v16[0]);
      v6 = v14;
    }
    else
    {
      if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || (v9[28] & 1) == 0 )
        goto LABEL_18;
      WPP_SF_dd(
        *((_QWORD *)v9 + 2),
        10,
        WPP_95f9c60226ea37d25f480d31695c5346_Traceguids,
        (unsigned int)v8[4 * (_QWORD)v7],
        v8[4 * (_QWORD)v7 + 1]);
    }
    if ( v6 )
    {
      EapLm::RasAuthAttributeDestroy(v5, v4);
      EapHost::EapException::Throw(L"RasAuthAttributeInsert", &qword_18003A720, v6);
    }
    v9 = WPP_GLOBAL_Control;
LABEL_18:
    v7 = (EapLm *)((char *)v7 + 1);
  }
  if ( *(_QWORD *)a1 )
    EapLm::RasAuthAttributeDestroy(*(HLOCAL *)a1, v4);
  *(_QWORD *)a1 = v5;
  EapHost::AutoAttributes::~AutoAttributes((EapHost::AutoAttributes *)v16);
  return a1;
}

```

## disassembly

```asm
0x180029b80  push    rbx
0x180029b82  push    rbp
0x180029b83  push    rsi
0x180029b84  push    rdi
0x180029b85  push    r14
0x180029b87  sub     rsp, 60h
0x180029b8b  mov     rbx, rcx
0x180029b8e  cmp     dword ptr [rdx], 0
0x180029b91  jnz     short loc_180029B9D
0x180029b93  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x180029b98  jmp     loc_180029CC2
0x180029b9d  xorps   xmm0, xmm0
0x180029ba0  movdqu  xmmword ptr [rsp+88h+var_58], xmm0; void *
0x180029ba6  mov     [rsp+88h+var_48], 0
0x180029baf  movups  [rsp+88h+var_40], xmm0
0x180029bb4  lea     rcx, [rsp+88h+var_58]; this
0x180029bb9  call    ?Assign@AutoAttributes@EapHost@@AEAAXAEBU_EAP_ATTRIBUTES@@@Z; EapHost::AutoAttributes::Assign(_EAP_ATTRIBUTES const &)
0x180029bbe  nop
0x180029bbf  mov     rcx, [rsp+88h+var_48]; this
0x180029bc4  call    ?RasAuthAttributeCreate@EapLm@@YAPEAU_RAS_AUTH_ATTRIBUTE@@_K@Z; EapLm::RasAuthAttributeCreate(unsigned __int64)
0x180029bc9  mov     rsi, rax
0x180029bcc  test    rax, rax
0x180029bcf  jnz     short loc_180029BDE
0x180029bd1  lea     rcx, aRasauthattribu_2; "RasAuthAttributeCreate"
0x180029bd8  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180029bde  xor     ebp, ebp
0x180029be0  xor     edi, edi
0x180029be2  mov     r14, [rsp+88h+var_58]
0x180029be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180029bee  cmp     rdi, [rsp+88h+var_48]
0x180029bf3  jnb     loc_180029CA8
0x180029bf9  mov     r9, rdi
0x180029bfc  add     r9, r9
0x180029bff  mov     r10d, [r14+r9*8+4]
0x180029c04  test    r10d, r10d
0x180029c07  jz      short loc_180029C46
0x180029c09  mov     rdx, [r14+r9*8+8]; enum _RAS_AUTH_ATTRIBUTE_TYPE_
0x180029c0e  test    rdx, rdx
0x180029c11  jz      short loc_180029C46
0x180029c13  mov     r8d, [r14+r9*8]
0x180029c17  mov     ecx, r8d; this
0x180029c1a  call    ?IsPointerValue@EapLm@@YA_NW4_RAS_AUTH_ATTRIBUTE_TYPE_@@@Z; EapLm::IsPointerValue(_RAS_AUTH_ATTRIBUTE_TYPE_)
0x180029c1f  mov     rcx, rdi; this
0x180029c22  test    al, al
0x180029c24  jz      short loc_180029C2D
0x180029c26  mov     qword ptr [rsp+88h+var_60], rdx
0x180029c2b  jmp     short loc_180029C35
0x180029c2d  movzx   eax, byte ptr [rdx]
0x180029c30  mov     qword ptr [rsp+88h+var_60], rax; unsigned int
0x180029c35  mov     [rsp+88h+var_68], r10d; int
0x180029c3a  mov     rdx, rsi; unsigned __int64
0x180029c3d  call    ?RasAuthAttributeInsert@EapLm@@YAK_KPEAU_RAS_AUTH_ATTRIBUTE@@W4_RAS_AUTH_ATTRIBUTE_TYPE_@@HKPEAX@Z; EapLm::RasAuthAttributeInsert(unsigned __int64,_RAS_AUTH_ATTRIBUTE *,_RAS_AUTH_ATTRIBUTE_TYPE_,int,ulong,void *)
0x180029c42  mov     ebp, eax
0x180029c44  jmp     short loc_180029C76
0x180029c46  lea     rax, WPP_GLOBAL_Control
0x180029c4d  cmp     rcx, rax
0x180029c50  jz      short loc_180029C81
0x180029c52  test    byte ptr [rcx+1Ch], 1
0x180029c56  jz      short loc_180029C81
0x180029c58  mov     edx, 0Ah
0x180029c5d  mov     [rsp+88h+var_68], r10d
0x180029c62  mov     r9d, [r14+r9*8]
0x180029c66  lea     r8, WPP_95f9c60226ea37d25f480d31695c5346_Traceguids
0x180029c6d  mov     rcx, [rcx+10h]
0x180029c71  call    WPP_SF_dd
0x180029c76  test    ebp, ebp
0x180029c78  jnz     short loc_180029C89
0x180029c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c81  inc     rdi
0x180029c84  jmp     loc_180029BEE
0x180029c89  mov     rcx, rsi; hMem
0x180029c8c  call    ?RasAuthAttributeDestroy@EapLm@@YAXPEAU_RAS_AUTH_ATTRIBUTE@@@Z; EapLm::RasAuthAttributeDestroy(_RAS_AUTH_ATTRIBUTE *)
0x180029c91  mov     r8d, ebp; int
0x180029c94  lea     rdx, qword_18003A720; wchar_t *
0x180029c9b  lea     rcx, aRasauthattribu; "RasAuthAttributeInsert"
0x180029ca2  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180029ca8  mov     rcx, [rbx]; hMem
0x180029cab  test    rcx, rcx
0x180029cae  jz      short loc_180029CB5
0x180029cb0  call    ?RasAuthAttributeDestroy@EapLm@@YAXPEAU_RAS_AUTH_ATTRIBUTE@@@Z; EapLm::RasAuthAttributeDestroy(_RAS_AUTH_ATTRIBUTE *)
0x180029cb5  mov     [rbx], rsi
0x180029cb8  lea     rcx, [rsp+88h+var_58]; this
0x180029cbd  call    ??1AutoAttributes@EapHost@@QEAA@XZ; EapHost::AutoAttributes::~AutoAttributes(void)
0x180029cc2  mov     rax, rbx
0x180029cc5  add     rsp, 60h
0x180029cc9  pop     r14
0x180029ccb  pop     rdi
0x180029ccc  pop     rsi
0x180029ccd  pop     rbp
0x180029cce  pop     rbx
0x180029ccf  retn
```
