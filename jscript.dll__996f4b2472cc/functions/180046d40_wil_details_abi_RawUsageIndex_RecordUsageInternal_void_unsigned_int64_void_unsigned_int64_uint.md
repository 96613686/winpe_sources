# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180046d40`
- end: `0x180046f53`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `531`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180046618`

## callees

- `0x18004670c`
- `0x180046d40`
- `0x180047054`
- `0x18004def0`
- `0x180053138`
- `0x18005b44c`
- `0x18005b800`
- `0x180096686`

## import_xrefs

- `msvcrt!memmove_s` at `0x180046ee2`
- `msvcrt!memmove_s` at `0x180046ee2`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v10; // rdi
  char v11; // r14
  bool v12; // al
  unsigned int v13; // r12d
  __int64 v14; // r9
  unsigned __int64 v15; // r15
  int v16; // ecx
  unsigned __int8 *InsertionPointOrIncrement; // rax
  unsigned __int64 Size; // r8
  __int64 v20; // rdx
  char v21; // cl
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // r9
  __int16 v26; // [rsp+30h] [rbp-40h] BYREF
  char v27; // [rsp+32h] [rbp-3Eh]
  int v28; // [rsp+34h] [rbp-3Ch]
  unsigned __int16 v29; // [rsp+38h] [rbp-38h]
  void *Buf2[2]; // [rsp+40h] [rbp-30h]
  __int16 v31; // [rsp+50h] [rbp-20h] BYREF
  char v32; // [rsp+52h] [rbp-1Eh]
  unsigned int v33; // [rsp+54h] [rbp-1Ch]
  __int16 v34; // [rsp+58h] [rbp-18h]
  __int64 v35; // [rsp+60h] [rbp-10h]
  void *v36; // [rsp+68h] [rbp-8h]
  unsigned __int8 *v37; // [rsp+B0h] [rbp+40h] BYREF
  void *Buf1; // [rsp+B8h] [rbp+48h]

  Buf1 = a2;
  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v10 = (unsigned __int8 *)(v6 + 10);
  v26 = *((_WORD *)this + 1);
  v11 = 0;
  v27 = *((_BYTE *)this + 4);
  v37 = v10;
  v28 = 0;
  v29 = 0;
  *(_OWORD *)Buf2 = 0;
  while ( 1 )
  {
    v12 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v26,
            &v37,
            *((unsigned __int8 **)this + 4));
    v13 = a6;
    v14 = 0;
    v15 = a5;
    if ( !v12 )
    {
      v10 = v37;
      *((_QWORD *)this + 4) = v37;
LABEL_17:
      Buf2[1] = Buf1;
      v28 = 1;
      v29 = a3;
      Buf2[0] = 0;
      Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v26);
      goto LABEL_18;
    }
    if ( a3 == v29 )
    {
      v16 = memcmp_0(Buf1, Buf2[1], a3);
      v14 = 0;
    }
    else
    {
      v16 = a3 - v29;
    }
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v26,
                                    v37,
                                    a4,
                                    v15,
                                    v13);
      v14 = 0;
      v37 = InsertionPointOrIncrement;
      v10 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        v11 = 1;
        goto LABEL_14;
      }
      return 1;
    }
    v10 = wil::details_abi::RawUsageIndex::SkipValues(this, (struct wil::details_abi::UsageIndexProperty *)&v26, v37);
    v37 = v10;
  }
  v37 = v10;
LABEL_14:
  Size = 0;
  if ( !v11 )
    goto LABEL_17;
LABEL_18:
  v20 = *((unsigned __int16 *)this + 3);
  v21 = *((_BYTE *)this + 8);
  v31 = v20;
  v32 = v21;
  v33 = v13;
  v34 = v15;
  v35 = v14;
  v36 = a4;
  if ( (_WORD)v20 )
    v22 = v20;
  else
    v22 = (unsigned __int16)v15 + 2LL;
  if ( v21 == 1 )
  {
    v22 += 2;
  }
  else if ( v21 == 2 )
  {
    v22 += 4;
  }
  v23 = *((_QWORD *)this + 5);
  v24 = v22 + Size;
  v25 = *((_QWORD *)this + 4);
  if ( ((v23 - v25) & -(__int64)(v25 < v23)) >= v22 + Size )
  {
    memmove_s(&v10[v24], v23 - v24 - (_QWORD)v10, v10, v25 - (_QWORD)v10);
    *((_QWORD *)this + 4) += v24;
    if ( v11 )
    {
      if ( v27 )
        wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v26, v28 + 1);
    }
    else
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v26,
        &v37,
        *((unsigned __int8 **)this + 4));
    }
    wil::details_abi::UsageIndexProperty::Write(
      (wil::details_abi::UsageIndexProperty *)&v31,
      &v37,
      *((unsigned __int8 **)this + 4));
    *((_BYTE *)this + 56) = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180046d40  mov     [rsp-38h+arg_10], rbx
0x180046d45  mov     [rsp-38h+Buf1], rdx
0x180046d4a  push    rbp
0x180046d4b  push    rsi
0x180046d4c  push    rdi
0x180046d4d  push    r12
0x180046d4f  push    r13
0x180046d51  push    r14
0x180046d53  push    r15
0x180046d55  mov     rbp, rsp
0x180046d58  sub     rsp, 70h
0x180046d5c  mov     rdi, [rcx+18h]
0x180046d60  mov     rbx, rcx
0x180046d63  xor     ecx, ecx
0x180046d65  mov     r13, r9
0x180046d68  mov     rsi, r8
0x180046d6b  test    rdi, rdi
0x180046d6e  jz      loc_180046F38
0x180046d74  movzx   eax, word ptr [rbx+2]
0x180046d78  add     rdi, 0Ah
0x180046d7c  mov     [rbp+var_40], ax
0x180046d80  xorps   xmm0, xmm0
0x180046d83  mov     al, [rbx+4]
0x180046d86  mov     r14b, cl
0x180046d89  mov     [rbp+var_3E], al
0x180046d8c  mov     [rbp+arg_0], rdi
0x180046d90  mov     [rbp+var_3C], ecx
0x180046d93  mov     [rbp+var_38], cx
0x180046d97  movdqu  xmmword ptr [rbp+Buf2], xmm0
0x180046d9c  mov     r8, [rbx+20h]; unsigned __int8 *
0x180046da0  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180046da4  lea     rcx, [rbp+var_40]; this
0x180046da8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180046dad  mov     r12d, [rbp+arg_28]
0x180046db1  xor     r9d, r9d
0x180046db4  mov     r15, [rbp+arg_20]
0x180046db8  test    al, al
0x180046dba  jz      loc_180046E42
0x180046dc0  movzx   eax, [rbp+var_38]
0x180046dc4  cmp     rsi, rax
0x180046dc7  jnz     short loc_180046DE0
0x180046dc9  mov     rdx, [rbp+Buf2+8]; Buf2
0x180046dcd  mov     r8, rsi; Size
0x180046dd0  mov     rcx, [rbp+Buf1]; Buf1
0x180046dd4  call    memcmp_0
0x180046dd9  mov     ecx, eax
0x180046ddb  xor     r9d, r9d
0x180046dde  jmp     short loc_180046DE8
0x180046de0  movzx   eax, [rbp+var_38]
0x180046de4  mov     ecx, esi
0x180046de6  sub     ecx, eax
0x180046de8  test    ecx, ecx
0x180046dea  js      short loc_180046E34
0x180046dec  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180046df0  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180046df4  mov     rcx, rbx; this
0x180046df7  jz      short loc_180046E07
0x180046df9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180046dfe  mov     rdi, rax
0x180046e01  mov     [rbp+arg_0], rax
0x180046e05  jmp     short loc_180046D9C
0x180046e07  mov     [rsp+70h+var_48], r12d; unsigned int
0x180046e0c  mov     r9, r13; void *
0x180046e0f  mov     [rsp+70h+var_50], r15; unsigned __int64
0x180046e14  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180046e19  xor     r9d, r9d
0x180046e1c  mov     [rbp+arg_0], rax
0x180046e20  mov     rdi, rax
0x180046e23  test    rax, rax
0x180046e26  jnz     short loc_180046E2F
0x180046e28  mov     al, 1
0x180046e2a  jmp     loc_180046F3A
0x180046e2f  mov     r14b, 1
0x180046e32  jmp     short loc_180046E38
0x180046e34  mov     [rbp+arg_0], rdi
0x180046e38  mov     r8, r9
0x180046e3b  test    r14b, r14b
0x180046e3e  jz      short loc_180046E4A
0x180046e40  jmp     short loc_180046E6D
0x180046e42  mov     rdi, [rbp+arg_0]
0x180046e46  mov     [rbx+20h], rdi
0x180046e4a  mov     rax, [rbp+Buf1]
0x180046e4e  lea     rcx, [rbp+var_40]; this
0x180046e52  mov     [rbp+Buf2+8], rax
0x180046e56  mov     [rbp+var_3C], 1
0x180046e5d  mov     [rbp+var_38], si
0x180046e61  mov     [rbp+Buf2], r9
0x180046e65  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180046e6a  mov     r8, rax
0x180046e6d  movzx   edx, word ptr [rbx+6]
0x180046e71  mov     cl, [rbx+8]
0x180046e74  mov     [rbp+var_20], dx
0x180046e78  mov     [rbp+var_1E], cl
0x180046e7b  mov     [rbp+var_1C], r12d
0x180046e7f  mov     [rbp+var_18], r15w
0x180046e84  mov     [rbp+var_10], r9
0x180046e88  mov     [rbp+var_8], r13
0x180046e8c  test    dx, dx
0x180046e8f  jnz     short loc_180046E9B
0x180046e91  movzx   eax, r15w
0x180046e95  add     rax, 2
0x180046e99  jmp     short loc_180046E9E
0x180046e9b  mov     rax, rdx
0x180046e9e  cmp     cl, 1
0x180046ea1  jnz     short loc_180046EA9
0x180046ea3  add     rax, 2
0x180046ea7  jmp     short loc_180046EB2
0x180046ea9  cmp     cl, 2
0x180046eac  jnz     short loc_180046EB2
0x180046eae  add     rax, 4
0x180046eb2  mov     rdx, [rbx+28h]
0x180046eb6  lea     rsi, [rax+r8]
0x180046eba  mov     r9, [rbx+20h]
0x180046ebe  mov     rcx, rdx
0x180046ec1  sub     rcx, r9
0x180046ec4  cmp     r9, rdx
0x180046ec7  sbb     rax, rax
0x180046eca  and     rax, rcx
0x180046ecd  cmp     rax, rsi
0x180046ed0  jb      short loc_180046F38
0x180046ed2  sub     rdx, rsi
0x180046ed5  lea     rcx, [rsi+rdi]; Destination
0x180046ed9  sub     rdx, rdi; DestinationSize
0x180046edc  sub     r9, rdi; SourceSize
0x180046edf  mov     r8, rdi; Source
0x180046ee2  call    cs:__imp_memmove_s
0x180046ee9  nop     dword ptr [rax+rax+00h]
0x180046eee  add     [rbx+20h], rsi
0x180046ef2  test    r14b, r14b
0x180046ef5  jnz     short loc_180046F0A
0x180046ef7  mov     r8, [rbx+20h]; unsigned __int8 *
0x180046efb  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180046eff  lea     rcx, [rbp+var_40]; this
0x180046f03  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180046f08  jmp     short loc_180046F1E
0x180046f0a  cmp     [rbp+var_3E], 0
0x180046f0e  jz      short loc_180046F1E
0x180046f10  mov     edx, [rbp+var_3C]
0x180046f13  lea     rcx, [rbp+var_40]; this
0x180046f17  inc     edx; unsigned int
0x180046f19  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180046f1e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180046f22  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180046f26  lea     rcx, [rbp+var_20]; this
0x180046f2a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180046f2f  mov     byte ptr [rbx+38h], 1
0x180046f33  jmp     loc_180046E28
0x180046f38  xor     al, al
0x180046f3a  mov     rbx, [rsp+70h+arg_10]
0x180046f42  add     rsp, 70h
0x180046f46  pop     r15
0x180046f48  pop     r14
0x180046f4a  pop     r13
0x180046f4c  pop     r12
0x180046f4e  pop     rdi
0x180046f4f  pop     rsi
0x180046f50  pop     rbp
0x180046f51  retn
```
