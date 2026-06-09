# ControlBlock::ControlBlock(_RADIUS_EXTENSION_POINT,IASTL::IASRequest &)

- ea: `0x180014f94`
- end: `0x18001518a`
- name: `??0ControlBlock@@QEAA@W4_RADIUS_EXTENSION_POINT@@AEAVIASRequest@IASTL@@@Z`
- size: `502`
- prototype: `ControlBlock *(ControlBlock *__hidden this, enum _RADIUS_EXTENSION_POINT, struct IASTL::IASRequest *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180012740`

## callees

- `0x18000b2dc`
- `0x18000baa8`
- `0x18000dfa4`
- `0x180013af8`
- `0x180014f00`
- `0x180014f94`
- `0x18001543c`
- `0x18002e010`

## string_xrefs

- `0x180015061`: `rcAccessRequest`
- `0x180015068`: `rcAccessAccept`
- `0x180015144`: `rcAccessReject`
- `0x18001515b`: `rcAccessChallenge`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
ControlBlock *__fastcall ControlBlock::ControlBlock(
        ControlBlock *this,
        enum _RADIUS_EXTENSION_POINT a2,
        struct IASTL::IASRequest *a3)
{
  char *v6; // r14
  __int64 v7; // rcx
  int Request; // eax
  const char *v9; // rdi
  const char *v10; // rbx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int128 v16; // [rsp+20h] [rbp-68h] BYREF
  int v17; // [rsp+30h] [rbp-58h]
  char v18; // [rsp+34h] [rbp-54h]

  v6 = (char *)this + 48;
  *((_QWORD *)this + 6) = *(_QWORD *)a3;
  v7 = *((_QWORD *)a3 + 1);
  *((_QWORD *)v6 + 1) = v7;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  AttributeArray::AttributeArray((ControlBlock *)((char *)this + 64), a3);
  AttributeArray::AttributeArray((ControlBlock *)((char *)this + 184), a3);
  AttributeArray::AttributeArray((ControlBlock *)((char *)this + 304), a3);
  AttributeArray::AttributeArray((ControlBlock *)((char *)this + 424), a3);
  *(_DWORD *)this = 48;
  *((_DWORD *)this + 1) = 1;
  *((_DWORD *)this + 2) = a2;
  Request = IASTL::IASRequest::get_Request(v6);
  if ( Request )
  {
    if ( Request == 1 )
    {
      *((_DWORD *)this + 3) = 4;
      v9 = "rcAccountingRequest";
      v10 = "rcAccountingResponse";
      goto LABEL_7;
    }
    *((_DWORD *)this + 3) = 0;
    v9 = "rcUnknown";
  }
  else
  {
    *((_DWORD *)this + 3) = 1;
    v9 = "rcAccessRequest";
  }
  v10 = "rcAccessAccept";
LABEL_7:
  v11 = IASTL::IASRequest::get_Response(v6) - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 == 1 )
            *((_DWORD *)this + 4) = 256;
          else
            *((_DWORD *)this + 4) = 0;
        }
        else
        {
          *((_DWORD *)this + 4) = 5;
        }
      }
      else
      {
        *((_DWORD *)this + 4) = 11;
      }
    }
    else
    {
      *((_DWORD *)this + 4) = 3;
    }
  }
  else
  {
    *((_DWORD *)this + 4) = 2;
  }
  *((_QWORD *)this + 3) = ControlBlock::GetRequest;
  *((_QWORD *)this + 4) = ControlBlock::GetResponse;
  *((_QWORD *)this + 5) = ControlBlock::SetResponseType;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  IASTL::IASAttributeVector::load((IASTL::IASAttributeVector *)&v16, *((struct IAttributesRaw **)this + 7));
  AttributeArray::Assign(
    (ControlBlock *)((char *)this + 64),
    v9,
    rcAccessRequest,
    (const struct IASTL::IASAttributeVector *)&v16);
  AttributeArray::Assign(
    (ControlBlock *)((char *)this + 184),
    v10,
    rcAccessAccept,
    (const struct IASTL::IASAttributeVector *)&v16);
  AttributeArray::Assign(
    (ControlBlock *)((char *)this + 304),
    "rcAccessReject",
    rcAccessReject,
    (const struct IASTL::IASAttributeVector *)&v16);
  AttributeArray::Assign(
    (ControlBlock *)((char *)this + 424),
    "rcAccessChallenge",
    rcAccessChallenge,
    (const struct IASTL::IASAttributeVector *)&v16);
  IASTL::IASAttributeVector::~IASAttributeVector((IASTL::IASAttributeVector *)&v16);
  return this;
}

```

## disassembly

```asm
0x180014f94  mov     [rsp+arg_0], rcx
0x180014f99  push    rbx
0x180014f9a  push    rbp
0x180014f9b  push    rsi
0x180014f9c  push    rdi
0x180014f9d  push    r12
0x180014f9f  push    r13
0x180014fa1  push    r14
0x180014fa3  push    r15
0x180014fa5  sub     rsp, 48h
0x180014fa9  mov     rbx, r8
0x180014fac  mov     edi, edx
0x180014fae  mov     rsi, rcx
0x180014fb1  lea     r14, [rcx+30h]
0x180014fb5  mov     rax, [r8]
0x180014fb8  mov     [r14], rax
0x180014fbb  mov     rcx, [r8+8]
0x180014fbf  mov     [r14+8], rcx
0x180014fc3  mov     rax, [rcx]
0x180014fc6  mov     rax, [rax+8]
0x180014fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fcf  nop
0x180014fd0  mov     rdx, rbx; struct IASTL::IASRequest *
0x180014fd3  lea     rcx, [rsi+40h]; this
0x180014fd7  call    ??0AttributeArray@@QEAA@AEAVIASRequest@IASTL@@@Z; AttributeArray::AttributeArray(IASTL::IASRequest &)
0x180014fdc  nop
0x180014fdd  lea     r15, [rsi+0B8h]
0x180014fe4  mov     rdx, rbx; struct IASTL::IASRequest *
0x180014fe7  mov     rcx, r15; this
0x180014fea  call    ??0AttributeArray@@QEAA@AEAVIASRequest@IASTL@@@Z; AttributeArray::AttributeArray(IASTL::IASRequest &)
0x180014fef  nop
0x180014ff0  lea     r12, [rsi+130h]
0x180014ff7  mov     rdx, rbx; struct IASTL::IASRequest *
0x180014ffa  mov     rcx, r12; this
0x180014ffd  call    ??0AttributeArray@@QEAA@AEAVIASRequest@IASTL@@@Z; AttributeArray::AttributeArray(IASTL::IASRequest &)
0x180015002  nop
0x180015003  lea     r13, [rsi+1A8h]
0x18001500a  mov     rdx, rbx; struct IASTL::IASRequest *
0x18001500d  mov     rcx, r13; this
0x180015010  call    ??0AttributeArray@@QEAA@AEAVIASRequest@IASTL@@@Z; AttributeArray::AttributeArray(IASTL::IASRequest &)
0x180015015  nop
0x180015016  mov     dword ptr [rsi], 30h ; '0'
0x18001501c  mov     ebx, 1
0x180015021  mov     [rsi+4], ebx
0x180015024  mov     [rsi+8], edi
0x180015027  mov     rcx, r14
0x18001502a  call    ?get_Request@IASRequest@IASTL@@QEBA?AW4_IASREQUEST@@XZ; IASTL::IASRequest::get_Request(void)
0x18001502f  test    eax, eax
0x180015031  jz      short loc_18001505E
0x180015033  cmp     eax, ebx
0x180015035  jz      short loc_180015047
0x180015037  mov     dword ptr [rsi+0Ch], 0
0x18001503e  lea     rdi, aRcunknown; "rcUnknown"
0x180015045  jmp     short loc_180015068
0x180015047  mov     dword ptr [rsi+0Ch], 4
0x18001504e  lea     rdi, aRcaccountingre; "rcAccountingRequest"
0x180015055  lea     rbx, aRcaccountingre_0; "rcAccountingResponse"
0x18001505c  jmp     short loc_18001506F
0x18001505e  mov     [rsi+0Ch], ebx
0x180015061  lea     rdi, aRcaccessreques; "rcAccessRequest"
0x180015068  lea     rbx, aRcaccessaccept; "rcAccessAccept"
0x18001506f  mov     rcx, r14
0x180015072  call    ?get_Response@IASRequest@IASTL@@QEBA?AW4_IASRESPONSE@@XZ; IASTL::IASRequest::get_Response(void)
0x180015077  mov     r14d, 0Bh
0x18001507d  sub     eax, 1
0x180015080  jz      short loc_1800150C0
0x180015082  sub     eax, 1
0x180015085  jz      short loc_1800150B7
0x180015087  sub     eax, 1
0x18001508a  jz      short loc_1800150B1
0x18001508c  sub     eax, 1
0x18001508f  jz      short loc_1800150A8
0x180015091  cmp     eax, 1
0x180015094  jz      short loc_18001509F
0x180015096  mov     dword ptr [rsi+10h], 0
0x18001509d  jmp     short loc_1800150C7
0x18001509f  mov     dword ptr [rsi+10h], 100h
0x1800150a6  jmp     short loc_1800150C7
0x1800150a8  mov     dword ptr [rsi+10h], 5
0x1800150af  jmp     short loc_1800150C7
0x1800150b1  mov     [rsi+10h], r14d
0x1800150b5  jmp     short loc_1800150C7
0x1800150b7  mov     dword ptr [rsi+10h], 3
0x1800150be  jmp     short loc_1800150C7
0x1800150c0  mov     dword ptr [rsi+10h], 2
0x1800150c7  lea     rax, ?GetRequest@ControlBlock@@CAPEAU_RADIUS_ATTRIBUTE_ARRAY@@PEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@@Z; ControlBlock::GetRequest(_RADIUS_EXTENSION_CONTROL_BLOCK *)
0x1800150ce  mov     [rsi+18h], rax
0x1800150d2  lea     rax, ?GetResponse@ControlBlock@@CAPEAU_RADIUS_ATTRIBUTE_ARRAY@@PEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@W4_RADIUS_CODE@@@Z; ControlBlock::GetResponse(_RADIUS_EXTENSION_CONTROL_BLOCK *,_RADIUS_CODE)
0x1800150d9  mov     [rsi+20h], rax
0x1800150dd  lea     rax, ?SetResponseType@ControlBlock@@CAKPEAU_RADIUS_EXTENSION_CONTROL_BLOCK@@W4_RADIUS_CODE@@@Z; ControlBlock::SetResponseType(_RADIUS_EXTENSION_CONTROL_BLOCK *,_RADIUS_CODE)
0x1800150e4  mov     [rsi+28h], rax
0x1800150e8  xorps   xmm0, xmm0
0x1800150eb  movdqu  [rsp+88h+var_68], xmm0
0x1800150f1  mov     [rsp+88h+var_58], 0
0x1800150f9  mov     [rsp+88h+var_54], 0
0x1800150fe  mov     rdx, [rsi+38h]; struct IAttributesRaw *
0x180015102  lea     rcx, [rsp+88h+var_68]; this
0x180015107  call    ?load@IASAttributeVector@IASTL@@QEAAKPEAUIAttributesRaw@@@Z; IASTL::IASAttributeVector::load(IAttributesRaw *)
0x18001510c  lea     r9, [rsp+88h+var_68]; struct IASTL::IASAttributeVector *
0x180015111  mov     r8d, 1; enum _RADIUS_CODE
0x180015117  mov     rdx, rdi; char *
0x18001511a  lea     rcx, [rsi+40h]; this
0x18001511e  call    ?Assign@AttributeArray@@QEAAXPEBDW4_RADIUS_CODE@@AEBVIASAttributeVector@IASTL@@@Z; AttributeArray::Assign(char const *,_RADIUS_CODE,IASTL::IASAttributeVector const &)
0x180015123  lea     r9, [rsp+88h+var_68]; struct IASTL::IASAttributeVector *
0x180015128  mov     r8d, 2; enum _RADIUS_CODE
0x18001512e  mov     rdx, rbx; char *
0x180015131  mov     rcx, r15; this
0x180015134  call    ?Assign@AttributeArray@@QEAAXPEBDW4_RADIUS_CODE@@AEBVIASAttributeVector@IASTL@@@Z; AttributeArray::Assign(char const *,_RADIUS_CODE,IASTL::IASAttributeVector const &)
0x180015139  lea     r9, [rsp+88h+var_68]; struct IASTL::IASAttributeVector *
0x18001513e  mov     r8d, 3; enum _RADIUS_CODE
0x180015144  lea     rdx, aRcaccessreject; "rcAccessReject"
0x18001514b  mov     rcx, r12; this
0x18001514e  call    ?Assign@AttributeArray@@QEAAXPEBDW4_RADIUS_CODE@@AEBVIASAttributeVector@IASTL@@@Z; AttributeArray::Assign(char const *,_RADIUS_CODE,IASTL::IASAttributeVector const &)
0x180015153  lea     r9, [rsp+88h+var_68]; struct IASTL::IASAttributeVector *
0x180015158  mov     r8d, r14d; enum _RADIUS_CODE
0x18001515b  lea     rdx, aRcaccesschalle; "rcAccessChallenge"
0x180015162  mov     rcx, r13; this
0x180015165  call    ?Assign@AttributeArray@@QEAAXPEBDW4_RADIUS_CODE@@AEBVIASAttributeVector@IASTL@@@Z; AttributeArray::Assign(char const *,_RADIUS_CODE,IASTL::IASAttributeVector const &)
0x18001516a  nop
0x18001516b  lea     rcx, [rsp+88h+var_68]; this
0x180015170  call    ??1IASAttributeVector@IASTL@@QEAA@XZ; IASTL::IASAttributeVector::~IASAttributeVector(void)
0x180015175  nop
0x180015176  mov     rax, rsi
0x180015179  add     rsp, 48h
0x18001517d  pop     r15
0x18001517f  pop     r14
0x180015181  pop     r13
0x180015183  pop     r12
0x180015185  pop     rdi
0x180015186  pop     rsi
0x180015187  pop     rbp
0x180015188  pop     rbx
0x180015189  retn
```
