# CClfsMarshallingContext::ReserveAndAppendLog(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,_CLS_LSN const &,_CLS_LSN const &,ulong,_CLS_LSN &,_OVERLAPPED *)

- ea: `0x180013178`
- end: `0x18001359d`
- name: `?ReserveAndAppendLog@CClfsMarshallingContext@@QEAAKPEAU_CLS_WRITE_ENTRY@@KKKQEA_JAEBT_CLS_LSN@@2KAEAT3@PEAU_OVERLAPPED@@@Z`
- size: `1061`
- prototype: `unsigned int __usercall@<eax>(CClfsMarshallingContext *__hidden this@<rcx>, struct _CLS_WRITE_ENTRY *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, __int64 *const, const union _CLS_LSN *, const union _CLS_LSN *, char, union _CLS_LSN *, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000cff0`
- `0x18000d170`

## callees

- `0x18000e534`
- `0x18000e8e4`
- `0x18000efa0`
- `0x1800101c8`
- `0x1800106f8`
- `0x180013178`
- `0x180014dce`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800133b1`
- `ntdll!RtlLeaveCriticalSection` at `0x18001358a`
- `ntdll!RtlLeaveCriticalSection` at `0x180015b28`
- `ntdll!RtlLeaveCriticalSection` at `0x180015b4c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800133b1`
- `ntdll!RtlLeaveCriticalSection` at `0x18001358a`
- `ntdll!RtlLeaveCriticalSection` at `0x180015b28`
- `ntdll!RtlLeaveCriticalSection` at `0x180015b4c`
- `ntdll!RtlEnterCriticalSection` at `0x1800131ff`
- `ntdll!RtlEnterCriticalSection` at `0x180013390`
- `ntdll!RtlEnterCriticalSection` at `0x1800131ff`
- `ntdll!RtlEnterCriticalSection` at `0x180013390`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::ReserveAndAppendLog(
        CClfsMarshallingContext *this,
        struct _CLS_WRITE_ENTRY *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        __int64 *const a6,
        const union _CLS_LSN *a7,
        const union _CLS_LSN *a8,
        char a9,
        union _CLS_LSN *a10,
        struct _OVERLAPPED *a11)
{
  struct _CLS_WRITE_ENTRY *v11; // r13
  unsigned int Iocb; // esi
  int v14; // edi
  char v15; // bl
  struct _RTL_CRITICAL_SECTION *v17; // r15
  CLogIocb **v18; // r15
  CLogIocb *v19; // r13
  __int64 v20; // rbx
  CLFS_LSN *v21; // rdi
  unsigned __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int appended; // eax
  unsigned int v25; // ebx
  struct _CLFS_RECORD_HEADER *v26; // rax
  CLogIocb *v27; // rax
  __int64 v28; // rbx
  CLFS_LSN *v29; // rdi
  unsigned __int64 v30; // rax
  unsigned int v31; // ecx
  union _CLS_LSN *v32; // rcx
  CLogIocb *v33; // rax
  char v34; // [rsp+60h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+68h] [rbp-80h]
  unsigned int v36; // [rsp+70h] [rbp-78h] BYREF
  unsigned int v37; // [rsp+74h] [rbp-74h]
  int v38; // [rsp+78h] [rbp-70h]
  char v39; // [rsp+7Ch] [rbp-6Ch]
  unsigned int v40; // [rsp+80h] [rbp-68h] BYREF
  unsigned int v41; // [rsp+84h] [rbp-64h] BYREF
  struct _CLFS_RECORD_HEADER *v42; // [rsp+88h] [rbp-60h] BYREF
  int v43; // [rsp+90h] [rbp-58h]
  CLogIocb *v44; // [rsp+98h] [rbp-50h]
  struct _CLS_WRITE_ENTRY *v45; // [rsp+A0h] [rbp-48h]

  v11 = a2;
  v42 = 0;
  Iocb = 0;
  v40 = 0;
  v36 = 0;
  v41 = 0;
  v14 = 0;
  v38 = 0;
  v15 = 0;
  v34 = 0;
  if ( !*((_DWORD *)this + 31) )
    return 6605;
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
  v35 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  if ( !*((_BYTE *)this + 100) )
  {
    v18 = (CLogIocb **)((char *)this + 160);
    if ( !*((_QWORD *)this + 20) )
    {
      Iocb = CClfsMarshallingContext::AllocateIocb(this, 1, (char *)this + 160);
      if ( Iocb || (v19 = *v18) == 0 )
      {
LABEL_33:
        v17 = v35;
        goto LABEL_34;
      }
      v20 = *((unsigned int *)this + 32);
      v21 = (CLFS_LSN *)*((_QWORD *)v19 + 8);
      memset_0(v21, 0, 0x70u);
      LOBYTE(v21->offset.idxRecord) = 21;
      v21[3] = CLFS_LSN_INVALID;
      v21[4] = CLFS_LSN_INVALID;
      v21[5].offset.idxRecord = 112;
      v22 = (unsigned __int64)(v20 - 40) >> 9;
      HIWORD(v21->ullOffset) = v22;
      WORD2(v21->ullOffset) = v22;
      *((_DWORD *)v19 + 18) = 112;
      v21[5].offset.idxRecord = 0;
      v11 = a2;
      v15 = 0;
      v14 = v38;
    }
    v45 = v11;
    v23 = a3;
    v37 = a3;
    while ( !v15 )
    {
      appended = CClfsMarshallingContext::AppendRecord(
                   this,
                   v11,
                   v23,
                   a4,
                   a5,
                   a6,
                   a9,
                   (CLFS_LSN **)&v42,
                   &v36,
                   &v41,
                   &v40);
      Iocb = appended;
      if ( appended )
      {
        if ( appended != 234 )
          goto LABEL_33;
        v25 = v40;
        if ( !v40 )
          CLogIocb::GetLastRecord(*v18, &v42);
        v26 = v42;
        if ( !v42 )
        {
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
          CClfsMarshallingContext::FreeIocb(this, *v18);
          *v18 = 0;
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
          goto LABEL_33;
        }
        *((_BYTE *)v42 + 36) |= 1u;
        v38 = v25 + v14;
        v43 = v25 + v14;
        *a10 = *(union _CLS_LSN *)v26;
        Iocb = CClfsMarshallingContext::AppendWriteBlockToFlushQueue(this, 0, 0, 0);
        if ( Iocb )
          goto LABEL_33;
        Iocb = CClfsMarshallingContext::AllocateIocb(this, 1, (char *)this + 160);
        if ( Iocb )
          goto LABEL_33;
        v27 = *v18;
        v44 = v27;
        if ( !v27 )
          goto LABEL_33;
        v28 = *((unsigned int *)this + 32);
        v29 = (CLFS_LSN *)*((_QWORD *)v27 + 8);
        memset_0(v29, 0, 0x70u);
        LOBYTE(v29->offset.idxRecord) = 21;
        v29[3] = CLFS_LSN_INVALID;
        v29[4] = CLFS_LSN_INVALID;
        v29[5].offset.idxRecord = 112;
        v30 = (unsigned __int64)(v28 - 40) >> 9;
        HIWORD(v29->ullOffset) = v30;
        WORD2(v29->ullOffset) = v30;
        *((_DWORD *)v44 + 18) = 112;
        v29[5].offset.idxRecord = 0;
        if ( a3 )
        {
          v11 += v36;
          v45 = v11;
          v31 = v41;
          v11->Buffer = (char *)v11->Buffer + v41;
          v11->ByteLength -= v31;
          v23 = v37 - v36;
          v37 -= v36;
          v36 = 0;
        }
        else
        {
          v23 = v37;
        }
        v15 = v34;
      }
      else
      {
        if ( a3 )
        {
          v32 = (union _CLS_LSN *)v42;
          *((_BYTE *)v42 + 36) |= 1u;
          v32[1] = *a7;
          v32[2] = *a8;
          v38 = v40 + v14;
          v43 = v40 + v14;
          *a10 = *v32;
        }
        v15 = 1;
        v34 = 1;
        v39 = 1;
        v23 = v37;
      }
      v14 = v38;
    }
    v33 = *v18;
    if ( *v18 && (a9 & 3) != 0 && (*((_DWORD *)v33 + 18) || *((_QWORD *)v33 + 10)) )
    {
      *((_WORD *)v33 + 14) |= 2u;
      Iocb = CClfsMarshallingContext::AppendWriteBlockToFlushQueue(this, 0, a9 & 2, a11);
    }
    goto LABEL_33;
  }
  Iocb = 6643;
LABEL_34:
  RtlLeaveCriticalSection(v17);
  return Iocb;
}

```

## disassembly

```asm
0x180013178  mov     rax, rsp
0x18001317b  mov     [rax+20h], r9d
0x18001317f  mov     [rax+18h], r8d
0x180013183  mov     [rax+10h], rdx
0x180013187  mov     [rax+8], rcx
0x18001318b  push    rbx
0x18001318c  push    rsi
0x18001318d  push    rdi
0x18001318e  push    r12
0x180013190  push    r13
0x180013192  push    r14
0x180013194  push    r15
0x180013196  sub     rsp, 0B0h
0x18001319d  mov     r13, rdx
0x1800131a0  mov     r14, rcx
0x1800131a3  xor     r12d, r12d
0x1800131a6  mov     [rax-60h], r12
0x1800131aa  mov     esi, r12d
0x1800131ad  mov     [rax-68h], r12d
0x1800131b1  mov     [rax-78h], r12d
0x1800131b5  mov     [rax-64h], r12d
0x1800131b9  mov     edi, r12d
0x1800131bc  mov     [rax-70h], r12d
0x1800131c0  mov     bl, r12b
0x1800131c3  mov     [rsp+0E8h+var_88], bl
0x1800131c7  mov     [rsp+0E8h+var_87], r12b
0x1800131cc  mov     [rsp+0E8h+var_86], r12b
0x1800131d1  cmp     [rcx+7Ch], r12d
0x1800131d5  jnz     short loc_1800131F0
0x1800131d7  mov     eax, 19CDh
0x1800131dc  add     rsp, 0B0h
0x1800131e3  pop     r15
0x1800131e5  pop     r14
0x1800131e7  pop     r13
0x1800131e9  pop     r12
0x1800131eb  pop     rdi
0x1800131ec  pop     rsi
0x1800131ed  pop     rbx
0x1800131ee  retn
0x1800131f0  lea     r15, [rcx+120h]
0x1800131f7  mov     [rsp+0E8h+var_80], r15
0x1800131fc  mov     rcx, r15; CriticalSection
0x1800131ff  call    cs:__imp_RtlEnterCriticalSection
0x180013206  nop     dword ptr [rax+rax+00h]
0x18001320b  mov     [rsp+0E8h+var_87], 1
0x180013210  cmp     [r14+64h], r12b
0x180013214  jz      short loc_180013224
0x180013216  mov     esi, 19F3h
0x18001321b  mov     [rsp+0E8h+var_84], esi
0x18001321f  jmp     loc_180013587
0x180013224  lea     r15, [r14+0A0h]
0x18001322b  cmp     [r15], r12
0x18001322e  jnz     loc_1800132BE
0x180013234  mov     r8, r15
0x180013237  mov     edx, 1
0x18001323c  mov     rcx, r14
0x18001323f  call    ?AllocateIocb@CClfsMarshallingContext@@AEAAKW4_LOGIOCB_TYPE@1@AEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocb(CClfsMarshallingContext::_LOGIOCB_TYPE,CLogIocb * &)
0x180013244  mov     esi, eax
0x180013246  mov     [rsp+0E8h+var_84], eax
0x18001324a  test    eax, eax
0x18001324c  jnz     loc_180013582
0x180013252  mov     r13, [r15]
0x180013255  test    r13, r13
0x180013258  jz      loc_180013582
0x18001325e  mov     ebx, [r14+80h]
0x180013265  mov     rdi, [r13+40h]
0x180013269  lea     r12d, [rax+70h]
0x18001326d  mov     r8d, r12d; Size
0x180013270  xor     edx, edx; Val
0x180013272  mov     rcx, rdi; void *
0x180013275  call    memset_0
0x18001327a  mov     byte ptr [rdi], 15h
0x18001327d  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180013284  mov     [rdi+18h], rax
0x180013288  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001328f  mov     [rdi+20h], rax
0x180013293  mov     [rdi+28h], r12d
0x180013297  lea     rax, [rbx-28h]
0x18001329b  shr     rax, 9
0x18001329f  mov     [rdi+6], ax
0x1800132a3  mov     [rdi+4], ax
0x1800132a7  mov     [r13+48h], r12d
0x1800132ab  mov     [rdi+28h], esi
0x1800132ae  mov     r13, [rsp+0E8h+arg_8]
0x1800132b6  mov     bl, [rsp+0E8h+var_88]
0x1800132ba  mov     edi, [rsp+0E8h+var_70]
0x1800132be  mov     [rsp+0E8h+var_48], r13
0x1800132c6  mov     eax, [rsp+0E8h+arg_10]
0x1800132cd  mov     [rsp+0E8h+var_74], eax
0x1800132d1  mov     r12d, dword ptr [rsp+0E8h+arg_40]
0x1800132d9  test    bl, bl
0x1800132db  jnz     loc_180013540
0x1800132e1  lea     rcx, [rsp+0E8h+var_68]
0x1800132e9  mov     [rsp+0E8h+var_98], rcx; unsigned int *
0x1800132ee  lea     rcx, [rsp+0E8h+var_64]
0x1800132f6  mov     [rsp+0E8h+var_A0], rcx; unsigned int *
0x1800132fb  lea     rcx, [rsp+0E8h+var_78]
0x180013300  mov     [rsp+0E8h+var_A8], rcx; unsigned int *
0x180013305  lea     rcx, [rsp+0E8h+var_60]
0x18001330d  mov     [rsp+0E8h+var_B0], rcx; struct _CLFS_RECORD_HEADER **
0x180013312  mov     dword ptr [rsp+0E8h+var_B8], r12d; char
0x180013317  mov     rcx, [rsp+0E8h+arg_28]
0x18001331f  mov     [rsp+0E8h+var_C0], rcx; __int64 *
0x180013324  mov     ecx, [rsp+0E8h+arg_20]
0x18001332b  mov     [rsp+0E8h+var_C8], ecx; unsigned int
0x18001332f  mov     r9d, [rsp+0E8h+arg_18]; unsigned int
0x180013337  mov     r8d, eax; unsigned int
0x18001333a  mov     rdx, r13; struct _CLS_WRITE_ENTRY *
0x18001333d  mov     rcx, r14; this
0x180013340  call    ?AppendRecord@CClfsMarshallingContext@@AEAAKPEAU_CLS_WRITE_ENTRY@@KKKQEA_JKAEAPEAU_CLFS_RECORD_HEADER@@AEAK33@Z; CClfsMarshallingContext::AppendRecord(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,ulong,_CLFS_RECORD_HEADER * &,ulong &,ulong &,ulong &)
0x180013345  mov     esi, eax
0x180013347  mov     [rsp+0E8h+var_84], eax
0x18001334b  test    eax, eax
0x18001334d  jz      loc_1800134CB
0x180013353  cmp     eax, 0EAh
0x180013358  jnz     loc_180013582
0x18001335e  mov     ebx, [rsp+0E8h+var_68]
0x180013365  test    ebx, ebx
0x180013367  jnz     short loc_180013379
0x180013369  lea     rdx, [rsp+0E8h+var_60]; struct _CLFS_RECORD_HEADER **
0x180013371  mov     rcx, [r15]; this
0x180013374  call    ?GetLastRecord@CLogIocb@@QEAAKAEAPEAU_CLFS_RECORD_HEADER@@@Z; CLogIocb::GetLastRecord(_CLFS_RECORD_HEADER * &)
0x180013379  mov     rax, [rsp+0E8h+var_60]
0x180013381  test    rax, rax
0x180013384  jnz     short loc_1800133C2
0x180013386  lea     rbx, [r14+148h]
0x18001338d  mov     rcx, rbx; CriticalSection
0x180013390  call    cs:__imp_RtlEnterCriticalSection
0x180013397  nop     dword ptr [rax+rax+00h]
0x18001339c  mov     rdx, [r15]; struct CLogIocb *
0x18001339f  mov     rcx, r14; this
0x1800133a2  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x1800133a7  mov     qword ptr [r15], 0
0x1800133ae  mov     rcx, rbx; CriticalSection
0x1800133b1  call    cs:__imp_RtlLeaveCriticalSection
0x1800133b8  nop     dword ptr [rax+rax+00h]
0x1800133bd  jmp     loc_180013582
0x1800133c2  or      byte ptr [rax+24h], 1
0x1800133c6  add     edi, ebx
0x1800133c8  mov     [rsp+0E8h+var_70], edi
0x1800133cc  mov     [rsp+0E8h+var_58], edi
0x1800133d3  mov     rax, [rax]
0x1800133d6  mov     rcx, [rsp+0E8h+arg_48]
0x1800133de  mov     [rcx], rax
0x1800133e1  xor     r9d, r9d; struct _OVERLAPPED *
0x1800133e4  xor     r8d, r8d; unsigned int
0x1800133e7  xor     edx, edx; unsigned __int8
0x1800133e9  mov     rcx, r14; this
0x1800133ec  call    ?AppendWriteBlockToFlushQueue@CClfsMarshallingContext@@AEAAKEKPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong,_OVERLAPPED *)
0x1800133f1  mov     esi, eax
0x1800133f3  mov     [rsp+0E8h+var_84], eax
0x1800133f7  test    eax, eax
0x1800133f9  jnz     loc_180013582
0x1800133ff  mov     r8, r15
0x180013402  lea     edx, [rax+1]
0x180013405  mov     rcx, r14
0x180013408  call    ?AllocateIocb@CClfsMarshallingContext@@AEAAKW4_LOGIOCB_TYPE@1@AEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocb(CClfsMarshallingContext::_LOGIOCB_TYPE,CLogIocb * &)
0x18001340d  mov     esi, eax
0x18001340f  mov     [rsp+0E8h+var_84], eax
0x180013413  test    eax, eax
0x180013415  jnz     loc_180013582
0x18001341b  mov     rax, [r15]
0x18001341e  mov     [rsp+0E8h+var_50], rax
0x180013426  test    rax, rax
0x180013429  jz      loc_180013582
0x18001342f  mov     ebx, [r14+80h]
0x180013436  mov     rdi, [rax+40h]
0x18001343a  xor     edx, edx; Val
0x18001343c  lea     r8d, [rsi+70h]; Size
0x180013440  mov     rcx, rdi; void *
0x180013443  call    memset_0
0x180013448  mov     byte ptr [rdi], 15h
0x18001344b  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180013452  mov     [rdi+18h], rax
0x180013456  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001345d  mov     [rdi+20h], rax
0x180013461  mov     dword ptr [rdi+28h], 70h ; 'p'
0x180013468  lea     rax, [rbx-28h]
0x18001346c  shr     rax, 9
0x180013470  mov     [rdi+6], ax
0x180013474  mov     [rdi+4], ax
0x180013478  mov     rax, [rsp+0E8h+var_50]
0x180013480  mov     dword ptr [rax+48h], 70h ; 'p'
0x180013487  mov     [rdi+28h], esi
0x18001348a  cmp     [rsp+0E8h+arg_10], esi
0x180013491  jbe     loc_18001352F
0x180013497  mov     eax, [rsp+0E8h+var_78]
0x18001349b  shl     rax, 4
0x18001349f  add     r13, rax
0x1800134a2  mov     [rsp+0E8h+var_48], r13
0x1800134aa  mov     ecx, [rsp+0E8h+var_64]
0x1800134b1  add     [r13+0], rcx
0x1800134b5  sub     [r13+8], ecx
0x1800134b9  mov     eax, [rsp+0E8h+var_74]
0x1800134bd  sub     eax, [rsp+0E8h+var_78]
0x1800134c1  mov     [rsp+0E8h+var_74], eax
0x1800134c5  mov     [rsp+0E8h+var_78], esi
0x1800134c9  jmp     short loc_180013533
0x1800134cb  cmp     [rsp+0E8h+arg_10], 0
0x1800134d3  jbe     short loc_18001351F
0x1800134d5  mov     rcx, [rsp+0E8h+var_60]
0x1800134dd  or      byte ptr [rcx+24h], 1
0x1800134e1  mov     rax, [rsp+0E8h+arg_30]
0x1800134e9  mov     rax, [rax]
0x1800134ec  mov     [rcx+8], rax
0x1800134f0  mov     rax, [rsp+0E8h+arg_38]
0x1800134f8  mov     rax, [rax]
0x1800134fb  mov     [rcx+10h], rax
0x1800134ff  add     edi, [rsp+0E8h+var_68]
0x180013506  mov     [rsp+0E8h+var_70], edi
0x18001350a  mov     [rsp+0E8h+var_58], edi
0x180013511  mov     rax, [rcx]
0x180013514  mov     rcx, [rsp+0E8h+arg_48]
0x18001351c  mov     [rcx], rax
0x18001351f  mov     bl, 1
0x180013521  mov     [rsp+0E8h+var_88], bl
0x180013525  mov     [rsp+0E8h+var_6C], bl
0x180013529  mov     eax, [rsp+0E8h+var_74]
0x18001352d  jmp     short loc_180013537
0x18001352f  mov     eax, [rsp+0E8h+var_74]
0x180013533  mov     bl, [rsp+0E8h+var_88]
0x180013537  mov     edi, [rsp+0E8h+var_70]
0x18001353b  jmp     loc_1800132D9
0x180013540  mov     rax, [r15]
0x180013543  test    rax, rax
0x180013546  jz      short loc_180013582
0x180013548  test    r12b, 3
0x18001354c  jz      short loc_180013582
0x18001354e  cmp     dword ptr [rax+48h], 0
0x180013552  ja      short loc_18001355B
0x180013554  cmp     qword ptr [rax+50h], 0
0x180013559  jz      short loc_180013582
0x18001355b  mov     ecx, 2
0x180013560  or      [rax+1Ch], cx
0x180013564  and     r12d, ecx
0x180013567  mov     r9, [rsp+0E8h+arg_50]; struct _OVERLAPPED *
0x18001356f  mov     r8d, r12d; unsigned int
0x180013572  xor     edx, edx; unsigned __int8
0x180013574  mov     rcx, r14; this
0x180013577  call    ?AppendWriteBlockToFlushQueue@CClfsMarshallingContext@@AEAAKEKPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong,_OVERLAPPED *)
0x18001357c  mov     esi, eax
0x18001357e  mov     [rsp+0E8h+var_84], eax
0x180013582  mov     r15, [rsp+0E8h+var_80]
0x180013587  mov     rcx, r15; CriticalSection
0x18001358a  call    cs:__imp_RtlLeaveCriticalSection
0x180013591  nop     dword ptr [rax+rax+00h]
0x180013596  mov     eax, esi
0x180013598  jmp     loc_1800131DC
0x180015b0b  push    rbp
0x180015b0d  sub     rsp, 60h
0x180015b11  mov     rbp, rdx
0x180015b14  cmp     byte ptr [rbp+61h], 0
0x180015b18  jz      short loc_180015B38
0x180015b1a  mov     rcx, [rbp+0F0h]
0x180015b21  add     rcx, 120h; CriticalSection
0x180015b28  call    cs:__imp_RtlLeaveCriticalSection
0x180015b2f  nop     dword ptr [rax+rax+00h]
0x180015b34  mov     byte ptr [rbp+61h], 0
0x180015b38  cmp     byte ptr [rbp+62h], 0
0x180015b3c  jz      short loc_180015B59
0x180015b3e  mov     rcx, [rbp+0F0h]
0x180015b45  add     rcx, 148h; CriticalSection
0x180015b4c  call    cs:__imp_RtlLeaveCriticalSection
0x180015b53  nop     dword ptr [rax+rax+00h]
0x180015b58  nop
0x180015b59  add     rsp, 60h
0x180015b5d  pop     rbp
0x180015b5e  retn
```
