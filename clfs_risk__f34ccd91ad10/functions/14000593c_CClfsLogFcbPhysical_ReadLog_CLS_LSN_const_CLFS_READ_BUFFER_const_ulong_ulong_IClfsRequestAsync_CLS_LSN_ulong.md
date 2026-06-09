# CClfsLogFcbPhysical::ReadLog(_CLS_LSN const &,_CLFS_READ_BUFFER const &,ulong,ulong,IClfsRequestAsync *,_CLS_LSN &,ulong &)

- ea: `0x14000593c`
- end: `0x140005efa`
- name: `?ReadLog@CClfsLogFcbPhysical@@AEAAJAEBT_CLS_LSN@@AEBU_CLFS_READ_BUFFER@@KKPEAUIClfsRequestAsync@@AEAT2@AEAK@Z`
- size: `1470`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, const union _CLS_LSN *, const struct _CLFS_READ_BUFFER *, unsigned int, unsigned int, struct IClfsRequestAsync *, union _CLS_LSN *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x1400075d0`
- `0x1400647c0`
- `0x140065110`

## callees

- `0x14000593c`
- `0x140005f00`
- `0x140007034`
- `0x140007470`
- `0x140008c40`
- `0x14000ed64`
- `0x140017f20`
- `0x140066e90`
- `0x14006b3fc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140005e77`
- `ntoskrnl!ObfDereferenceObject` at `0x140018bcc`
- `ntoskrnl!ObfDereferenceObject` at `0x140005e77`
- `ntoskrnl!ObfDereferenceObject` at `0x140018bcc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005bc9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005ddc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005bc9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005ddc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e5c`
- `ntoskrnl!KeClearEvent` at `0x140005cf0`
- `ntoskrnl!KeClearEvent` at `0x140005cf0`

## string_xrefs

- `0x140005cc7`: `CClfsLogFcbPhysical::ReadLog`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::ReadLog(
        CClfsLogFcbPhysical *this,
        const union _CLS_LSN *a2,
        const struct _CLFS_READ_BUFFER *a3,
        unsigned int a4,
        char a5,
        struct IClfsRequestAsync *a6,
        union _CLS_LSN *plsn,
        unsigned int *a8)
{
  struct _KEVENT *v10; // rdi
  unsigned int v11; // r8d
  enum _EVENT_TYPE v12; // ecx
  CClfsAuthContainer *Container; // r14
  NTSTATUS EventObject; // ebx
  char v15; // r12
  char v16; // cl
  char v17; // cl
  char v18; // al
  unsigned int v19; // eax
  CClfsLogFcbPhysical *v20; // r15
  char v21; // al
  ULONG v22; // eax
  struct _CLFS_IO_WORKITEM *v23; // r9
  unsigned __int64 v24; // r12
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // r15
  unsigned int v27; // r12d
  unsigned int v28; // r15d
  const CLFS_LSN *v29; // rax
  char v31; // [rsp+40h] [rbp-88h]
  char v32; // [rsp+41h] [rbp-87h]
  int v33; // [rsp+48h] [rbp-80h]
  int v34; // [rsp+4Ch] [rbp-7Ch]
  CLFS_CONTAINER_ID cidContainer; // [rsp+50h] [rbp-78h]
  unsigned __int64 v36; // [rsp+58h] [rbp-70h] BYREF
  PRKEVENT Event; // [rsp+60h] [rbp-68h] BYREF
  CClfsAuthContainer *v38; // [rsp+68h] [rbp-60h]
  __int128 v39; // [rsp+70h] [rbp-58h] BYREF
  __int64 v40; // [rsp+80h] [rbp-48h]
  CLFS_CONTAINER_ID v41; // [rsp+88h] [rbp-40h]
  int v42; // [rsp+8Ch] [rbp-3Ch]
  unsigned __int64 v43; // [rsp+90h] [rbp-38h] BYREF
  union _CLS_LSN v44; // [rsp+98h] [rbp-30h] BYREF
  char v47; // [rsp+F0h] [rbp+28h]

  v36 = 0;
  v10 = 0;
  Event = 0;
  v39 = 0;
  v40 = 0;
  v11 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
  if ( v11 - 1 > 0xFFF || (v11 & 0x1FF) != 0 || 0x1000 % v11 )
    return 3221225624LL;
  *a8 = 0;
  *plsn = CLFS_LSN_INVALID;
  if ( (unsigned __int64)ClfsLsnBlockOffset(a2) >= *((_QWORD *)this + 87) )
    return 3222929413LL;
  Container = 0;
  v38 = 0;
  EventObject = 0;
  v34 = 0;
  v32 = 0;
  v15 = 0;
  v31 = 0;
  cidContainer = 0;
  *plsn = *a2;
  v39 = *(_OWORD *)a3;
  v40 = *((_QWORD *)a3 + 2);
  if ( !a6 )
  {
    EventObject = ClfsCreateEventObject(v12, (PVOID *)&Event);
    if ( EventObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          61,
          (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
          (unsigned int)"CClfsLogFcbPhysical::ReadLog",
          225,
          EventObject);
      }
      v10 = Event;
      goto LABEL_60;
    }
    v10 = Event;
    KeClearEvent(Event);
  }
  v16 = a5;
  if ( (a5 & 2) != 0 )
  {
    v29 = (const CLFS_LSN *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, unsigned __int64 *))(*(_QWORD *)this
                                                                                                 + 352LL))(
                              this,
                              &v43);
    if ( ClfsLsnLess(a2, v29) )
    {
      EventObject = -1072037869;
      goto LABEL_60;
    }
    v16 = a5;
  }
  v17 = v16 & 1;
  v47 = v17;
  if ( !v17 )
  {
LABEL_12:
    v19 = 0;
    v33 = 0;
    v20 = this;
    while ( 1 )
    {
      if ( v19 >= a4 )
        goto LABEL_60;
      if ( v17 )
      {
        v21 = (_BYTE)v20 - 32;
        if ( v20 != (CClfsLogFcbPhysical *)-480LL )
        {
          if ( plsn->ullOffset >= *((_QWORD *)v20 + 60) )
            goto LABEL_60;
          v21 = 1;
        }
        if ( !v21 )
          goto LABEL_60;
      }
      if ( Container )
      {
        if ( cidContainer == plsn->offset.cidContainer )
          goto LABEL_22;
        (*(void (__fastcall **)(CClfsAuthContainer *))(*(_QWORD *)Container + 8LL))(Container);
        v38 = 0;
      }
      Container = CClfsLogFcbPhysical::GetContainer(v20, plsn->offset.cidContainer);
      v38 = Container;
      if ( Container )
      {
        cidContainer = plsn->offset.cidContainer;
        v41 = cidContainer;
LABEL_22:
        EventObject = 0;
        goto LABEL_23;
      }
      EventObject = -1072037875;
LABEL_23:
      if ( EventObject < 0 )
        goto LABEL_60;
      v22 = ClfsLsnBlockOffset(plsn);
      v24 = a4 - v33;
      v43 = v24;
      v25 = v22;
      v26 = (*((_QWORD *)v20 + 87) - (unsigned __int64)v22) >> 9;
      if ( v26 <= v24 )
      {
        if ( v32 || !a6 )
        {
          v15 = v31;
        }
        else
        {
          v32 = 1;
          v15 = 1;
          v31 = 1;
          v34 = (*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a6 + 16LL))(a6);
          v42 = v34;
        }
        v36 = v25;
        EventObject = CClfsAuthContainer::ReadSector(
                        Container,
                        v10,
                        a6,
                        v23,
                        (const struct _CLFS_READ_BUFFER *)&v39,
                        v26,
                        &v36);
        if ( (EventObject & 0xC0000000) == 0xC0000000 )
          goto LABEL_55;
        if ( v10 )
          EventObject = KeWaitForSingleObject(v10, Executive, 0, 0, 0);
        if ( EventObject < 0 )
          goto LABEL_60;
        v28 = (_DWORD)v26 << 9;
        *a8 += v28;
      }
      else
      {
        v36 = v22;
        EventObject = CClfsAuthContainer::ReadSector(
                        Container,
                        v10,
                        a6,
                        v23,
                        (const struct _CLFS_READ_BUFFER *)&v39,
                        a4 - v33,
                        &v36);
        if ( (EventObject & 0xC0000000) == 0xC0000000 )
        {
          v15 = v31;
LABEL_55:
          if ( v10 )
          {
            if ( v15 )
            {
              (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a6 + 88LL))(
                a6,
                (unsigned int)EventObject,
                0);
              v15 = 0;
              if ( v34 != (*(unsigned int (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a6 + 24LL))(a6) - 1 )
                KeWaitForSingleObject(v10, Executive, 0, 0, 0);
            }
          }
          goto LABEL_60;
        }
        v27 = (_DWORD)v24 << 9;
        v28 = v27;
        if ( v10 )
          EventObject = KeWaitForSingleObject(v10, Executive, 0, 0, 0);
        if ( EventObject < 0 )
        {
          v15 = v31;
          goto LABEL_60;
        }
        *a8 += v27;
      }
      LODWORD(v40) = v28 + v40;
      v33 += v28 >> 9;
      v20 = this;
      *plsn = **(union _CLS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(this, &v44, (unsigned int)plsn);
      v15 = v31;
      v19 = v33;
      v17 = v47;
    }
  }
  if ( this == (CClfsLogFcbPhysical *)-480LL )
  {
    v18 = 0;
LABEL_11:
    if ( v18 )
      goto LABEL_12;
    goto LABEL_31;
  }
  if ( a2->ullOffset < *((_QWORD *)this + 60) )
  {
    v18 = 1;
    goto LABEL_11;
  }
LABEL_31:
  EventObject = -1073741807;
LABEL_60:
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( v32 && v15 )
  {
    if ( EventObject < 0 )
      (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a6 + 88LL))(
        a6,
        (unsigned int)EventObject,
        0);
    (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a6 + 24LL))(a6);
  }
  if ( Container )
    (*(void (__fastcall **)(CClfsAuthContainer *))(*(_QWORD *)Container + 8LL))(Container);
  return (unsigned int)EventObject;
}

```

## disassembly

```asm
0x14000593c  mov     rax, rsp
0x14000593f  mov     [rax+10h], rbx
0x140005943  mov     [rax+18h], rsi
0x140005947  mov     [rax+20h], r9d
0x14000594b  mov     [rax+8], rcx
0x14000594f  push    rdi
0x140005950  push    r12
0x140005952  push    r13
0x140005954  push    r14
0x140005956  push    r15
0x140005958  sub     rsp, 0A0h
0x14000595f  mov     rsi, r8
0x140005962  mov     r15, rdx
0x140005965  mov     rbx, rcx
0x140005968  mov     qword ptr [rax-70h], 0
0x140005970  xor     edi, edi
0x140005972  mov     [rax-68h], rdi
0x140005976  xorps   xmm0, xmm0
0x140005979  movdqu  xmmword ptr [rax-58h], xmm0
0x14000597e  mov     [rax-48h], rdi
0x140005982  mov     rax, [rcx+2C8h]
0x140005989  mov     r8d, [rax+90h]
0x140005990  lea     eax, [r8-1]
0x140005994  cmp     eax, 0FFFh
0x140005999  ja      loc_140005EBE
0x14000599f  test    r8d, 1FFh
0x1400059a6  jnz     loc_140005EBE
0x1400059ac  xor     edx, edx
0x1400059ae  mov     eax, 1000h
0x1400059b3  div     r8d
0x1400059b6  test    edx, edx
0x1400059b8  jnz     loc_140005EBE
0x1400059be  mov     rax, [rsp+0C8h+arg_38]
0x1400059c6  mov     [rax], edi
0x1400059c8  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400059cf  mov     r13, [rsp+0C8h+plsn]
0x1400059d7  mov     [r13+0], rax
0x1400059db  mov     rcx, r15; plsn
0x1400059de  call    ClfsLsnBlockOffset
0x1400059e3  mov     eax, eax
0x1400059e5  cmp     rax, [rbx+2B8h]
0x1400059ec  jnb     loc_140005EC5
0x1400059f2  xor     r14d, r14d
0x1400059f5  mov     [rsp+0C8h+var_60], r14
0x1400059fa  xor     ebx, ebx
0x1400059fc  mov     [rsp+0C8h+var_84], ebx
0x140005a00  mov     [rsp+0C8h+var_7C], ebx
0x140005a04  mov     [rsp+0C8h+var_87], bl
0x140005a08  xor     r12b, r12b
0x140005a0b  mov     [rsp+0C8h+var_88], r12b
0x140005a10  mov     [rsp+0C8h+var_78], ebx
0x140005a14  mov     rax, [r15]
0x140005a17  mov     [r13+0], rax
0x140005a1b  movups  xmm0, xmmword ptr [rsi]
0x140005a1e  movups  [rsp+0C8h+var_58], xmm0
0x140005a23  movsd   xmm1, qword ptr [rsi+10h]
0x140005a28  movsd   [rsp+0C8h+var_48], xmm1
0x140005a31  mov     rsi, [rsp+0C8h+arg_28]
0x140005a39  test    rsi, rsi
0x140005a3c  jz      loc_140005C86
0x140005a42  mov     ecx, dword ptr [rsp+0C8h+arg_20]
0x140005a49  test    cl, 2
0x140005a4c  jnz     loc_140005D01
0x140005a52  and     ecx, 1
0x140005a55  mov     dword ptr [rsp+0C8h+arg_20], ecx
0x140005a5c  test    cl, cl
0x140005a5e  jz      short loc_140005A9F
0x140005a60  mov     rax, [rsp+0C8h+arg_0]
0x140005a68  add     rax, 1E0h
0x140005a6e  jz      loc_140005D45
0x140005a74  mov     ecx, [rax+4]
0x140005a77  cmp     [r15+4], ecx
0x140005a7b  ja      loc_140005C3A
0x140005a81  jnz     short loc_140005A8E
0x140005a83  mov     eax, [rax]
0x140005a85  cmp     [r15], eax
0x140005a88  jnb     loc_140005C3A
0x140005a8e  mov     al, 1
0x140005a90  mov     ecx, dword ptr [rsp+0C8h+arg_20]
0x140005a97  test    al, al
0x140005a99  jz      loc_140005C3A
0x140005a9f  xor     eax, eax
0x140005aa1  mov     [rsp+0C8h+var_80], eax
0x140005aa5  mov     r15, [rsp+0C8h+arg_0]
0x140005aad  cmp     eax, [rsp+0C8h+arg_18]
0x140005ab4  jnb     loc_140005E6F
0x140005aba  test    cl, cl
0x140005abc  jz      short loc_140005AEF
0x140005abe  lea     rax, [r15+1E0h]
0x140005ac5  test    rax, rax
0x140005ac8  jz      short loc_140005AE7
0x140005aca  mov     ecx, [rax+4]
0x140005acd  cmp     [r13+4], ecx
0x140005ad1  ja      loc_140005E6F
0x140005ad7  jnz     short loc_140005AE5
0x140005ad9  mov     eax, [rax]
0x140005adb  cmp     [r13+0], eax
0x140005adf  jnb     loc_140005E6F
0x140005ae5  mov     al, 1
0x140005ae7  test    al, al
0x140005ae9  jz      loc_140005E6F
0x140005aef  test    r14, r14
0x140005af2  jnz     loc_140005C52
0x140005af8  mov     edx, [r13+4]; unsigned int
0x140005afc  mov     rcx, r15; this
0x140005aff  call    ?GetContainer@CClfsLogFcbPhysical@@AEAAPEAVCClfsAuthContainer@@K@Z; CClfsLogFcbPhysical::GetContainer(ulong)
0x140005b04  mov     r14, rax
0x140005b07  mov     [rsp+0C8h+var_60], rax
0x140005b0c  test    rax, rax
0x140005b0f  jz      loc_140005C48
0x140005b15  mov     eax, [r13+4]
0x140005b19  mov     [rsp+0C8h+var_78], eax
0x140005b1d  mov     [rsp+0C8h+var_40], eax
0x140005b24  xor     ebx, ebx
0x140005b26  mov     [rsp+0C8h+var_84], ebx
0x140005b2a  test    ebx, ebx
0x140005b2c  js      loc_140005E6F
0x140005b32  mov     rcx, r13; plsn
0x140005b35  call    ClfsLsnBlockOffset
0x140005b3a  mov     r12d, [rsp+0C8h+arg_18]
0x140005b42  sub     r12d, [rsp+0C8h+var_80]
0x140005b47  mov     [rsp+0C8h+var_38], r12
0x140005b4f  mov     ebx, eax
0x140005b51  mov     r15, [r15+2B8h]
0x140005b58  sub     r15, rbx
0x140005b5b  shr     r15, 9
0x140005b5f  cmp     r15, r12
0x140005b62  jbe     loc_140005D4C
0x140005b68  mov     [rsp+0C8h+var_70], rbx
0x140005b6d  lea     rax, [rsp+0C8h+var_70]
0x140005b72  mov     [rsp+0C8h+var_98], rax; unsigned __int64 *
0x140005b77  mov     [rsp+0C8h+var_A0], r12d; unsigned int
0x140005b7c  lea     rax, [rsp+0C8h+var_58]
0x140005b81  mov     [rsp+0C8h+Timeout], rax; struct _CLFS_READ_BUFFER *
0x140005b86  mov     r8, rsi; struct IClfsRequestAsync *
0x140005b89  mov     rdx, rdi; struct _KEVENT *
0x140005b8c  mov     rcx, r14; this
0x140005b8f  call    ?ReadSector@CClfsAuthContainer@@QEAAJPEAU_KEVENT@@PEAUIClfsRequestAsync@@PEAU_CLFS_IO_WORKITEM@@AEBU_CLFS_READ_BUFFER@@KAEB_K@Z; CClfsAuthContainer::ReadSector(_KEVENT *,IClfsRequestAsync *,_CLFS_IO_WORKITEM *,_CLFS_READ_BUFFER const &,ulong,unsigned __int64 const &)
0x140005b94  mov     ebx, eax
0x140005b96  mov     [rsp+0C8h+var_84], eax
0x140005b9a  mov     ecx, 0C0000000h
0x140005b9f  and     eax, ecx
0x140005ba1  cmp     eax, ecx
0x140005ba3  jz      loc_140005E06
0x140005ba9  shl     r12d, 9
0x140005bad  mov     r15d, r12d
0x140005bb0  test    rdi, rdi
0x140005bb3  jz      short loc_140005BDB
0x140005bb5  mov     [rsp+0C8h+Timeout], 0; Timeout
0x140005bbe  xor     r9d, r9d; Alertable
0x140005bc1  xor     r8d, r8d; WaitMode
0x140005bc4  xor     edx, edx; WaitReason
0x140005bc6  mov     rcx, rdi; Object
0x140005bc9  call    cs:__imp_KeWaitForSingleObject
0x140005bd0  nop     dword ptr [rax+rax+00h]
0x140005bd5  mov     ebx, eax
0x140005bd7  mov     [rsp+0C8h+var_84], eax
0x140005bdb  test    ebx, ebx
0x140005bdd  js      loc_140005E6A
0x140005be3  mov     rax, [rsp+0C8h+arg_38]
0x140005beb  add     [rax], r12d
0x140005bee  add     dword ptr [rsp+0C8h+var_48], r15d
0x140005bf6  mov     eax, r15d
0x140005bf9  shr     eax, 9
0x140005bfc  add     [rsp+0C8h+var_80], eax
0x140005c00  mov     r9d, r15d
0x140005c03  mov     r8, r13; unsigned int
0x140005c06  lea     rdx, [rsp+0C8h+var_30]; union _CLS_LSN *
0x140005c0e  mov     r15, [rsp+0C8h+arg_0]
0x140005c16  mov     rcx, r15; this
0x140005c19  call    ?AddLsnOffset@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::AddLsnOffset(_CLS_LSN const &,ulong)
0x140005c1e  mov     rcx, [rax]
0x140005c21  mov     [r13+0], rcx
0x140005c25  mov     r12b, [rsp+0C8h+var_88]
0x140005c2a  mov     eax, [rsp+0C8h+var_80]
0x140005c2e  mov     ecx, dword ptr [rsp+0C8h+arg_20]
0x140005c35  jmp     loc_140005AAD
0x140005c3a  mov     ebx, 0C0000011h
0x140005c3f  mov     [rsp+0C8h+var_84], ebx
0x140005c43  jmp     loc_140005E6F
0x140005c48  mov     ebx, 0C01A000Dh
0x140005c4d  jmp     loc_140005B26
0x140005c52  mov     eax, [rsp+0C8h+var_78]
0x140005c56  cmp     eax, [r13+4]
0x140005c5a  jz      loc_140005B24
0x140005c60  test    r14, r14
0x140005c63  jz      loc_140005AF8
0x140005c69  mov     rax, [r14]
0x140005c6c  mov     rax, [rax+8]
0x140005c70  mov     rcx, r14
0x140005c73  call    _guard_dispatch_icall
0x140005c78  mov     [rsp+0C8h+var_60], 0
0x140005c81  jmp     loc_140005AF8
0x140005c86  lea     rdx, [rsp+0C8h+Event]; struct _KEVENT **
0x140005c8b  call    ?ClfsCreateEventObject@@YAJW4_EVENT_TYPE@@AEAPEAU_KEVENT@@@Z; ClfsCreateEventObject(_EVENT_TYPE,_KEVENT * &)
0x140005c90  mov     ebx, eax
0x140005c92  mov     [rsp+0C8h+var_84], eax
0x140005c96  test    eax, eax
0x140005c98  jns     short loc_140005CE8
0x140005c9a  lea     rax, WPP_GLOBAL_Control
0x140005ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ca8  cmp     rcx, rax
0x140005cab  jz      short loc_140005CDE
0x140005cad  test    dword ptr [rcx+2Ch], 8000000h
0x140005cb4  jz      short loc_140005CDE
0x140005cb6  mov     edx, 3Dh ; '='
0x140005cbb  mov     [rsp+0C8h+var_A0], ebx
0x140005cbf  mov     dword ptr [rsp+0C8h+Timeout], 6CE1h
0x140005cc7  lea     r9, aCclfslogfcbphy_19; "CClfsLogFcbPhysical::ReadLog"
0x140005cce  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x140005cd5  mov     rcx, [rcx+18h]
0x140005cd9  call    WPP_SF_slD
0x140005cde  mov     rdi, [rsp+0C8h+Event]
0x140005ce3  jmp     loc_140005E6F
0x140005ce8  mov     rdi, [rsp+0C8h+Event]
0x140005ced  mov     rcx, rdi; Event
0x140005cf0  call    cs:__imp_KeClearEvent
0x140005cf7  nop     dword ptr [rax+rax+00h]
0x140005cfc  jmp     loc_140005A42
0x140005d01  mov     rcx, [rsp+0C8h+arg_0]
0x140005d09  mov     rax, [rcx]
0x140005d0c  mov     rax, [rax+160h]
0x140005d13  lea     rdx, [rsp+0C8h+var_38]
0x140005d1b  call    _guard_dispatch_icall
0x140005d20  mov     rdx, rax; plsn2
0x140005d23  mov     rcx, r15; plsn1
0x140005d26  call    ClfsLsnLess
0x140005d2b  test    al, al
0x140005d2d  jz      short loc_140005D39
0x140005d2f  mov     ebx, 0C01A0013h
0x140005d34  jmp     loc_140005C3F
0x140005d39  mov     ecx, dword ptr [rsp+0C8h+arg_20]
0x140005d40  jmp     loc_140005A52
0x140005d45  xor     al, al
0x140005d47  jmp     loc_140005A97
0x140005d4c  cmp     [rsp+0C8h+var_87], 0
0x140005d51  jnz     short loc_140005D81
0x140005d53  test    rsi, rsi
0x140005d56  jz      short loc_140005D81
0x140005d58  mov     [rsp+0C8h+var_87], 1
0x140005d5d  mov     r12b, 1
0x140005d60  mov     [rsp+0C8h+var_88], r12b
0x140005d65  mov     rax, [rsi]
0x140005d68  mov     rax, [rax+10h]
0x140005d6c  mov     rcx, rsi
0x140005d6f  call    _guard_dispatch_icall
0x140005d74  mov     [rsp+0C8h+var_7C], eax
0x140005d78  mov     [rsp+0C8h+var_3C], eax
0x140005d7f  jmp     short loc_140005D86
0x140005d81  mov     r12b, [rsp+0C8h+var_88]
0x140005d86  mov     [rsp+0C8h+var_70], rbx
0x140005d8b  lea     rax, [rsp+0C8h+var_70]
0x140005d90  mov     [rsp+0C8h+var_98], rax; unsigned __int64 *
0x140005d95  mov     [rsp+0C8h+var_A0], r15d; unsigned int
0x140005d9a  lea     rax, [rsp+0C8h+var_58]
0x140005d9f  mov     [rsp+0C8h+Timeout], rax; struct _CLFS_READ_BUFFER *
0x140005da4  mov     r8, rsi; struct IClfsRequestAsync *
0x140005da7  mov     rdx, rdi; struct _KEVENT *
0x140005daa  mov     rcx, r14; this
0x140005dad  call    ?ReadSector@CClfsAuthContainer@@QEAAJPEAU_KEVENT@@PEAUIClfsRequestAsync@@PEAU_CLFS_IO_WORKITEM@@AEBU_CLFS_READ_BUFFER@@KAEB_K@Z; CClfsAuthContainer::ReadSector(_KEVENT *,IClfsRequestAsync *,_CLFS_IO_WORKITEM *,_CLFS_READ_BUFFER const &,ulong,unsigned __int64 const &)
0x140005db2  mov     ebx, eax
0x140005db4  mov     [rsp+0C8h+var_84], eax
0x140005db8  mov     ecx, 0C0000000h
0x140005dbd  and     eax, ecx
0x140005dbf  cmp     eax, ecx
0x140005dc1  jz      short loc_140005E0B
0x140005dc3  test    rdi, rdi
0x140005dc6  jz      short loc_140005DEE
0x140005dc8  mov     [rsp+0C8h+Timeout], 0; Timeout
0x140005dd1  xor     r9d, r9d; Alertable
0x140005dd4  xor     r8d, r8d; WaitMode
0x140005dd7  xor     edx, edx; WaitReason
0x140005dd9  mov     rcx, rdi; Object
0x140005ddc  call    cs:__imp_KeWaitForSingleObject
0x140005de3  nop     dword ptr [rax+rax+00h]
0x140005de8  mov     ebx, eax
0x140005dea  mov     [rsp+0C8h+var_84], eax
0x140005dee  test    ebx, ebx
0x140005df0  js      short loc_140005E6F
0x140005df2  shl     r15d, 9
0x140005df6  mov     rax, [rsp+0C8h+arg_38]
0x140005dfe  add     [rax], r15d
0x140005e01  jmp     loc_140005BEE
0x140005e06  mov     r12b, [rsp+0C8h+var_88]
0x140005e0b  test    rdi, rdi
0x140005e0e  jz      short loc_140005E6F
0x140005e10  test    r12b, r12b
0x140005e13  jz      short loc_140005E6F
0x140005e15  mov     rax, [rsi]
0x140005e18  mov     rax, [rax+58h]
0x140005e1c  xor     r8d, r8d
0x140005e1f  mov     edx, ebx
0x140005e21  mov     rcx, rsi
0x140005e24  call    _guard_dispatch_icall
0x140005e29  mov     rax, [rsi]
0x140005e2c  mov     rax, [rax+18h]
0x140005e30  mov     rcx, rsi
0x140005e33  call    _guard_dispatch_icall
0x140005e38  xor     r12b, r12b
0x140005e3b  mov     [rsp+0C8h+var_88], r12b
  ... truncated ...
```
