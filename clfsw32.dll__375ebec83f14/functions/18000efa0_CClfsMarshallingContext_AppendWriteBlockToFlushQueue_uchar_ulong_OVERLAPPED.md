# CClfsMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong,_OVERLAPPED *)

- ea: `0x18000efa0`
- end: `0x18000f3ef`
- name: `?AppendWriteBlockToFlushQueue@CClfsMarshallingContext@@AEAAKEKPEAU_OVERLAPPED@@@Z`
- size: `1103`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this, unsigned __int8, unsigned int, struct _OVERLAPPED *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e004`
- `0x18000fcdc`
- `0x180011854`
- `0x180013178`
- `0x180014328`

## callees

- `0x180009090`
- `0x18000efa0`
- `0x18000f95c`
- `0x1800101c8`
- `0x1800130a0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000f3b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f3c3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800157bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800157e5`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f3b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000f3c3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800157bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800157e5`
- `ntdll!RtlEnterCriticalSection` at `0x18000efe6`
- `ntdll!RtlEnterCriticalSection` at `0x18000f274`
- `ntdll!RtlEnterCriticalSection` at `0x18000efe6`
- `ntdll!RtlEnterCriticalSection` at `0x18000f274`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::AppendWriteBlockToFlushQueue(
        CClfsMarshallingContext *this,
        char a2,
        unsigned int a3,
        struct _OVERLAPPED *a4)
{
  unsigned __int64 v7; // rdi
  char v8; // r14
  struct _RTL_CRITICAL_SECTION *v9; // r15
  char v10; // si
  struct CLogIocb *v11; // rdx
  unsigned int v12; // edi
  int v13; // r8d
  union _CLS_LSN v14; // rax
  int v15; // r9d
  __int64 v16; // rax
  __int64 v17; // r15
  int v18; // r8d
  unsigned int v19; // r10d
  unsigned int v20; // edx
  unsigned int v21; // ecx
  int v22; // edx
  int v23; // ecx
  unsigned int appended; // eax
  __int64 v25; // rax
  char v26; // al
  union _CLS_LSN *v27; // r8
  __int64 v28; // rax
  _DWORD *v29; // rdx
  _DWORD *v30; // rcx
  unsigned int v31; // eax
  char v32; // al
  union _CLS_LSN *v33; // rdx
  unsigned int v34; // eax
  _QWORD *v35; // rcx
  DWORD v37; // [rsp+40h] [rbp-88h]
  union _CLS_LSN v38; // [rsp+90h] [rbp-38h] BYREF

  v7 = 0;
  v8 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  v10 = 1;
  if ( !*((_BYTE *)this + 100) )
  {
    v13 = *((_DWORD *)this + 34);
    if ( v13 )
    {
      v15 = -v13;
      v14.ullOffset = -v13 & (unsigned int)(v13 + *((_DWORD *)this + 32) + 983);
    }
    else
    {
      v14.ullOffset = 0;
      v15 = 0;
    }
    v38 = v14;
    v16 = *((_QWORD *)this + 20);
    if ( *(_DWORD *)(v16 + 76) )
    {
      v17 = *(_QWORD *)(v16 + 64);
      v19 = *(_DWORD *)(v16 + 72);
      v20 = v19 / 0x1FE;
      if ( v19 != 510 * (v19 / 0x1FE) )
        ++v20;
      if ( v13 )
        v21 = v15 & (v13 + v19 + ((2 * v20 + 7) & 0xFFFFFFF8) - 1);
      else
        v21 = 0;
      v22 = (unsigned __int16)(v21 >> 9);
      *(_WORD *)(v17 + 6) = v22;
      *(_WORD *)(v17 + 4) = v22;
      *(_DWORD *)(v17 + 104) = v21 - ((2 * v22 + 7) & 0xFFFFFFF8);
      v23 = *((_DWORD *)this + 34);
      if ( v23 )
      {
        v18 = -v23 & (v23 + (v22 << 9) - 1);
LABEL_18:
        if ( !a4 )
          v7 = *(_QWORD *)(*((_QWORD *)this + 20) + 56LL);
        appended = NtReserveAndAppendLogInternal(
                     *((void **)this + 6),
                     (void *)v17,
                     v18,
                     (__int64 *)(*((_QWORD *)this + 20) + 80LL),
                     (__int64 *)this + 24,
                     (__int64 *const)&v38,
                     a3,
                     (union _CLS_LSN *)(*((_QWORD *)this + 20) + 184LL),
                     v37,
                     (union _CLS_LSN *)(*((_QWORD *)this + 20) + 152LL),
                     (union _CLS_LSN *)this + 27,
                     0,
                     0,
                     v7,
                     (*((_DWORD *)this + 39) & 0x20) == 0,
                     a4);
        v12 = appended;
        if ( appended && appended != 997 && appended != 6647 )
        {
          if ( appended == 6643 )
          {
            *((_BYTE *)this + 100) = 1;
            a2 = 1;
          }
          if ( a2 )
          {
            CClfsMarshallingContext::FreeIocb(this, *((struct CLogIocb **)this + 20));
            *((_QWORD *)this + 20) = 0;
          }
          goto LABEL_62;
        }
        if ( (a3 & 2) == 0 || !v17 )
        {
LABEL_38:
          *((_QWORD *)this + 23) = *((_QWORD *)this + 22);
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
          v8 = 1;
          v27 = (union _CLS_LSN *)*((_QWORD *)this + 20);
          if ( !v27[9].offset.cidContainer )
          {
            if ( a4 )
            {
              v27[10].ullOffset = 0;
LABEL_52:
              v33 = (union _CLS_LSN *)((char *)this + 208);
              if ( this == (CClfsMarshallingContext *)-216LL || this == (CClfsMarshallingContext *)-208LL )
              {
                v10 = 0;
              }
              else
              {
                v34 = *((_DWORD *)this + 55);
                if ( v34 < *((_DWORD *)this + 53) )
                  goto LABEL_63;
                if ( v34 == *((_DWORD *)this + 53) )
                {
                  if ( *((_DWORD *)this + 54) > v33->offset.idxRecord )
                  {
                    v35 = (_QWORD *)((char *)this + 208);
                    goto LABEL_60;
                  }
LABEL_63:
                  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
                  goto LABEL_64;
                }
              }
              v35 = (_QWORD *)((char *)this + 208);
LABEL_60:
              if ( v10 )
              {
                *v35 = *((_QWORD *)this + 27);
                CClfsMarshallingContext::ReleaseFlushElements(this, v33);
              }
              goto LABEL_63;
            }
            CClfsMarshallingContext::FreeIocb(this, *((struct CLogIocb **)this + 20));
LABEL_51:
            *((_QWORD *)this + 20) = 0;
            goto LABEL_52;
          }
          CFlushQ::Enqueue((CClfsMarshallingContext *)((char *)this + 232), v27 + 19, (struct CLogIocb *const)v27);
          _InterlockedAdd((volatile signed __int32 *)this + 35, 1u);
          v28 = *((_QWORD *)this + 20);
          v29 = (_DWORD *)(v28 + 152);
          v30 = (_DWORD *)((char *)this + 200);
          if ( v28 == -152 || this == (CClfsMarshallingContext *)-200LL )
          {
            v32 = 0;
          }
          else
          {
            v31 = *(_DWORD *)(v28 + 156);
            if ( v31 < *((_DWORD *)this + 51) || v31 == *((_DWORD *)this + 51) && *v29 <= *v30 )
              goto LABEL_51;
            v32 = 1;
          }
          if ( v32 )
            *(_QWORD *)v30 = *(_QWORD *)v29;
          goto LABEL_51;
        }
        v25 = *((_QWORD *)this + 20);
        if ( v25 == -176 || this == (CClfsMarshallingContext *)-216LL )
        {
          v26 = 0;
        }
        else
        {
          if ( *(_QWORD *)(v25 + 176) >= *((_QWORD *)this + 27) )
          {
LABEL_35:
            if ( v12 != 997 && v12 != 6647 )
            {
              v12 = 6643;
LABEL_62:
              v8 = 0;
              goto LABEL_63;
            }
            goto LABEL_38;
          }
          v26 = 1;
        }
        if ( v26 )
          goto LABEL_38;
        goto LABEL_35;
      }
    }
    else
    {
      v17 = 0;
    }
    v18 = 0;
    goto LABEL_18;
  }
  v11 = (struct CLogIocb *)*((_QWORD *)this + 20);
  if ( v11 )
  {
    CClfsMarshallingContext::FreeIocb(this, v11);
    *((_QWORD *)this + 20) = 0;
  }
  v12 = 6643;
LABEL_64:
  if ( v12 == 6640 || v12 == 6643 )
  {
    v38 = CLFS_LSN_INVALID;
    CClfsMarshallingContext::ReleaseFlushElements(this, &v38);
  }
  if ( v8 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  RtlLeaveCriticalSection(v9);
  return v12;
}

```

## disassembly

```asm
0x18000efa0  mov     rax, rsp
0x18000efa3  mov     [rax+10h], rbx
0x18000efa7  mov     [rax+20h], rsi
0x18000efab  mov     [rax+18h], r8d
0x18000efaf  mov     [rax+8], rcx
0x18000efb3  push    rdi
0x18000efb4  push    r12
0x18000efb6  push    r13
0x18000efb8  push    r14
0x18000efba  push    r15
0x18000efbc  sub     rsp, 0A0h
0x18000efc3  mov     r13, r9
0x18000efc6  mov     r12b, dl
0x18000efc9  mov     rbx, rcx
0x18000efcc  xor     edi, edi
0x18000efce  mov     [rax-44h], edi
0x18000efd1  mov     [rax-47h], dil
0x18000efd5  xor     r14b, r14b
0x18000efd8  mov     [rax-48h], r14b
0x18000efdc  lea     r15, [rcx+120h]
0x18000efe3  mov     rcx, r15; CriticalSection
0x18000efe6  call    cs:__imp_RtlEnterCriticalSection
0x18000efed  nop     dword ptr [rax+rax+00h]
0x18000eff2  lea     esi, [rdi+1]
0x18000eff5  mov     [rsp+0C8h+var_47], sil
0x18000effd  xor     r11d, r11d
0x18000f000  cmp     [rbx+64h], r11b
0x18000f004  jz      short loc_18000F032
0x18000f006  mov     rdx, [rbx+0A0h]; struct CLogIocb *
0x18000f00d  test    rdx, rdx
0x18000f010  jz      short loc_18000F021
0x18000f012  mov     rcx, rbx; this
0x18000f015  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x18000f01a  mov     [rbx+0A0h], rdi
0x18000f021  mov     edi, 19F3h
0x18000f026  mov     [rsp+0C8h+var_44], edi
0x18000f02d  jmp     loc_18000F379
0x18000f032  mov     r8d, [rbx+88h]
0x18000f039  test    r8d, r8d
0x18000f03c  jnz     short loc_18000F046
0x18000f03e  mov     eax, r11d
0x18000f041  mov     r9d, r11d
0x18000f044  jmp     short loc_18000F05D
0x18000f046  mov     r9d, r8d
0x18000f049  neg     r9d
0x18000f04c  mov     eax, [rbx+80h]
0x18000f052  add     eax, 3D7h
0x18000f057  add     eax, r8d
0x18000f05a  and     eax, r9d
0x18000f05d  mov     qword ptr [rsp+0C8h+var_38], rax
0x18000f065  mov     rax, [rbx+0A0h]
0x18000f06c  cmp     [rax+4Ch], r11d
0x18000f070  jnz     short loc_18000F07D
0x18000f072  mov     r15, r11
0x18000f075  mov     r8d, r11d
0x18000f078  jmp     loc_18000F114
0x18000f07d  mov     r15, [rax+40h]
0x18000f081  mov     r10d, [rax+48h]
0x18000f085  mov     [rsp+0C8h+var_40], r11d
0x18000f08d  mov     eax, 80808081h
0x18000f092  mul     r10d
0x18000f095  shr     edx, 8
0x18000f098  mov     [rsp+0C8h+var_40], edx
0x18000f09f  imul    ecx, edx, 1FEh
0x18000f0a5  cmp     r10d, ecx
0x18000f0a8  jz      short loc_18000F0B3
0x18000f0aa  inc     edx
0x18000f0ac  mov     [rsp+0C8h+var_40], edx
0x18000f0b3  test    r8d, r8d
0x18000f0b6  jnz     short loc_18000F0BD
0x18000f0b8  mov     ecx, r11d
0x18000f0bb  jmp     short loc_18000F0D2
0x18000f0bd  lea     ecx, ds:7[rdx*2]
0x18000f0c4  and     ecx, 0FFFFFFF8h
0x18000f0c7  dec     ecx
0x18000f0c9  add     ecx, r10d
0x18000f0cc  add     ecx, r8d
0x18000f0cf  and     ecx, r9d
0x18000f0d2  mov     eax, ecx
0x18000f0d4  shr     eax, 9
0x18000f0d7  movzx   edx, ax
0x18000f0da  mov     [r15+6], dx
0x18000f0df  mov     [r15+4], dx
0x18000f0e4  lea     eax, ds:7[rdx*2]
0x18000f0eb  and     eax, 0FFFFFFF8h
0x18000f0ee  sub     ecx, eax
0x18000f0f0  mov     [r15+68h], ecx
0x18000f0f4  mov     ecx, [rbx+88h]
0x18000f0fa  test    ecx, ecx
0x18000f0fc  jz      loc_18000F075
0x18000f102  mov     r8d, edx
0x18000f105  shl     r8d, 9
0x18000f109  dec     r8d
0x18000f10c  add     r8d, ecx
0x18000f10f  neg     ecx
0x18000f111  and     r8d, ecx; unsigned int
0x18000f114  test    r13, r13
0x18000f117  jnz     short loc_18000F124
0x18000f119  mov     rax, [rbx+0A0h]
0x18000f120  mov     rdi, [rax+38h]
0x18000f124  mov     r9, [rbx+0A0h]
0x18000f12b  lea     r14, [rbx+0D8h]
0x18000f132  mov     edx, [rbx+9Ch]
0x18000f138  shr     edx, 5
0x18000f13b  not     dl
0x18000f13d  and     dl, sil
0x18000f140  lea     rax, [r9+98h]
0x18000f147  lea     rcx, [r9+0B8h]
0x18000f14e  lea     r10, [rbx+0C0h]
0x18000f155  add     r9, 50h ; 'P'; __int64 *
0x18000f159  mov     [rsp+0C8h+var_50], r13; struct _OVERLAPPED *
0x18000f15e  mov     [rsp+0C8h+var_58], dl; char
0x18000f162  mov     [rsp+0C8h+var_60], rdi; void *
0x18000f167  mov     [rsp+0C8h+var_68], r11; unsigned int *
0x18000f16c  mov     [rsp+0C8h+var_70], r11; struct _CLS_INFORMATION *
0x18000f171  mov     [rsp+0C8h+var_78], r14; union _CLS_LSN *
0x18000f176  mov     [rsp+0C8h+var_80], rax; union _CLS_LSN *
0x18000f17b  mov     [rsp+0C8h+var_90], rcx; union _CLS_LSN *
0x18000f180  mov     eax, [rsp+0C8h+arg_10]
0x18000f187  mov     [rsp+0C8h+var_98], eax; unsigned int
0x18000f18b  lea     rax, [rsp+0C8h+var_38]
0x18000f193  mov     [rsp+0C8h+var_A0], rax; __int64 *
0x18000f198  mov     [rsp+0C8h+var_A8], r10; __int64 *
0x18000f19d  mov     rdx, r15; void *
0x18000f1a0  mov     rcx, [rbx+30h]; void *
0x18000f1a4  call    ?NtReserveAndAppendLogInternal@@YAKPEAX0KPEA_J1QEA_JKPEAT_CLS_LSN@@PEAK33PEAU_CLS_INFORMATION@@40EPEAU_OVERLAPPED@@@Z; NtReserveAndAppendLogInternal(void *,void *,ulong,__int64 *,__int64 *,__int64 * const,ulong,_CLS_LSN *,ulong *,_CLS_LSN *,_CLS_LSN *,_CLS_INFORMATION *,ulong *,void *,uchar,_OVERLAPPED *)
0x18000f1a9  mov     edi, eax
0x18000f1ab  mov     [rsp+0C8h+var_44], eax
0x18000f1b2  test    eax, eax
0x18000f1b4  jz      short loc_18000F1FA
0x18000f1b6  cmp     eax, 3E5h
0x18000f1bb  jz      short loc_18000F1FA
0x18000f1bd  cmp     eax, 19F7h
0x18000f1c2  jz      short loc_18000F1FA
0x18000f1c4  cmp     eax, 19F3h
0x18000f1c9  jnz     short loc_18000F1D2
0x18000f1cb  mov     [rbx+64h], sil
0x18000f1cf  mov     r12b, sil
0x18000f1d2  test    r12b, r12b
0x18000f1d5  jz      loc_18000F36A
0x18000f1db  mov     rdx, [rbx+0A0h]; struct CLogIocb *
0x18000f1e2  mov     rcx, rbx; this
0x18000f1e5  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x18000f1ea  mov     qword ptr [rbx+0A0h], 0
0x18000f1f5  jmp     loc_18000F36A
0x18000f1fa  test    byte ptr [rsp+0C8h+arg_10], 2
0x18000f202  jz      short loc_18000F25F
0x18000f204  test    r15, r15
0x18000f207  jz      short loc_18000F25F
0x18000f209  mov     rax, [rbx+0A0h]
0x18000f210  lea     rcx, [rax+0B0h]
0x18000f217  test    rcx, rcx
0x18000f21a  jz      short loc_18000F238
0x18000f21c  test    r14, r14
0x18000f21f  jz      short loc_18000F238
0x18000f221  mov     eax, [rcx+4]
0x18000f224  cmp     eax, [r14+4]
0x18000f228  ja      short loc_18000F23E
0x18000f22a  jnz     short loc_18000F233
0x18000f22c  mov     eax, [r14]
0x18000f22f  cmp     [rcx], eax
0x18000f231  jnb     short loc_18000F23E
0x18000f233  mov     al, sil
0x18000f236  jmp     short loc_18000F23A
0x18000f238  xor     al, al
0x18000f23a  test    al, al
0x18000f23c  jnz     short loc_18000F25F
0x18000f23e  cmp     edi, 3E5h
0x18000f244  jz      short loc_18000F25F
0x18000f246  cmp     edi, 19F7h
0x18000f24c  jz      short loc_18000F25F
0x18000f24e  mov     edi, 19F3h
0x18000f253  mov     [rsp+0C8h+var_44], edi
0x18000f25a  jmp     loc_18000F36A
0x18000f25f  mov     rax, [rbx+0B0h]
0x18000f266  mov     [rbx+0B8h], rax
0x18000f26d  lea     rcx, [rbx+148h]; CriticalSection
0x18000f274  call    cs:__imp_RtlEnterCriticalSection
0x18000f27b  nop     dword ptr [rax+rax+00h]
0x18000f280  mov     r14b, sil
0x18000f283  mov     [rsp+0C8h+var_48], sil
0x18000f28b  mov     r8, [rbx+0A0h]; struct CLogIocb *
0x18000f292  cmp     dword ptr [r8+4Ch], 0
0x18000f297  jnz     short loc_18000F2B5
0x18000f299  test    r13, r13
0x18000f29c  jz      short loc_18000F2A8
0x18000f29e  mov     qword ptr [r8+50h], 0
0x18000f2a6  jmp     short loc_18000F31A
0x18000f2a8  mov     rdx, r8; struct CLogIocb *
0x18000f2ab  mov     rcx, rbx; this
0x18000f2ae  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x18000f2b3  jmp     short loc_18000F30F
0x18000f2b5  lea     rdx, [r8+98h]; union _CLS_LSN *
0x18000f2bc  lea     rcx, [rbx+0E8h]; this
0x18000f2c3  call    ?Enqueue@CFlushQ@@QEAAKAEBT_CLS_LSN@@QEAVCLogIocb@@@Z; CFlushQ::Enqueue(_CLS_LSN const &,CLogIocb * const)
0x18000f2c8  lock add [rbx+8Ch], esi
0x18000f2cf  mov     rax, [rbx+0A0h]
0x18000f2d6  lea     rdx, [rax+98h]
0x18000f2dd  lea     rcx, [rbx+0C8h]
0x18000f2e4  test    rdx, rdx
0x18000f2e7  jz      short loc_18000F303
0x18000f2e9  test    rcx, rcx
0x18000f2ec  jz      short loc_18000F303
0x18000f2ee  mov     eax, [rdx+4]
0x18000f2f1  cmp     eax, [rcx+4]
0x18000f2f4  jb      short loc_18000F30F
0x18000f2f6  jnz     short loc_18000F2FE
0x18000f2f8  mov     eax, [rcx]
0x18000f2fa  cmp     [rdx], eax
0x18000f2fc  jbe     short loc_18000F30F
0x18000f2fe  mov     al, sil
0x18000f301  jmp     short loc_18000F305
0x18000f303  xor     al, al
0x18000f305  test    al, al
0x18000f307  jz      short loc_18000F30F
0x18000f309  mov     rax, [rdx]
0x18000f30c  mov     [rcx], rax
0x18000f30f  mov     qword ptr [rbx+0A0h], 0
0x18000f31a  lea     rdx, [rbx+0D0h]; union _CLS_LSN *
0x18000f321  lea     rcx, [rbx+0D8h]
0x18000f328  test    rcx, rcx
0x18000f32b  jz      short loc_18000F34B
0x18000f32d  test    rdx, rdx
0x18000f330  jz      short loc_18000F34B
0x18000f332  mov     eax, [rcx+4]
0x18000f335  cmp     eax, [rdx+4]
0x18000f338  jb      short loc_18000F372
0x18000f33a  jnz     short loc_18000F34E
0x18000f33c  mov     eax, [rdx]
0x18000f33e  cmp     [rcx], eax
0x18000f340  jbe     short loc_18000F372
0x18000f342  lea     rcx, [rbx+0D0h]
0x18000f349  jmp     short loc_18000F351
0x18000f34b  xor     sil, sil
0x18000f34e  mov     rcx, rdx
0x18000f351  test    sil, sil
0x18000f354  jz      short loc_18000F372
0x18000f356  mov     rax, [rbx+0D8h]
0x18000f35d  mov     [rcx], rax
0x18000f360  mov     rcx, rbx; this
0x18000f363  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x18000f368  jmp     short loc_18000F372
0x18000f36a  mov     r14b, [rsp+0C8h+var_48]
0x18000f372  lea     r15, [rbx+120h]
0x18000f379  cmp     edi, 19F0h
0x18000f37f  jz      short loc_18000F389
0x18000f381  cmp     edi, 19F3h
0x18000f387  jnz     short loc_18000F3A8
0x18000f389  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000f390  mov     qword ptr [rsp+0C8h+var_38], rax
0x18000f398  lea     rdx, [rsp+0C8h+var_38]; union _CLS_LSN *
0x18000f3a0  mov     rcx, rbx; this
0x18000f3a3  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x18000f3a8  test    r14b, r14b
0x18000f3ab  jz      short loc_18000F3C0
0x18000f3ad  lea     rcx, [rbx+148h]; CriticalSection
0x18000f3b4  call    cs:__imp_RtlLeaveCriticalSection
0x18000f3bb  nop     dword ptr [rax+rax+00h]
0x18000f3c0  mov     rcx, r15; CriticalSection
0x18000f3c3  call    cs:__imp_RtlLeaveCriticalSection
0x18000f3ca  nop     dword ptr [rax+rax+00h]
0x18000f3cf  mov     eax, edi
0x18000f3d1  lea     r11, [rsp+0C8h+var_28]
0x18000f3d9  mov     rbx, [r11+38h]
0x18000f3dd  mov     rsi, [r11+48h]
0x18000f3e1  mov     rsp, r11
0x18000f3e4  pop     r15
0x18000f3e6  pop     r14
0x18000f3e8  pop     r13
0x18000f3ea  pop     r12
0x18000f3ec  pop     rdi
0x18000f3ed  retn
0x18001575e  push    rbp
0x180015760  sub     rsp, 80h
0x180015767  mov     rbp, rdx
0x18001576a  cmp     dword ptr [rbp+84h], 19F0h
0x180015774  jz      short loc_180015782
0x180015776  cmp     dword ptr [rbp+84h], 19F3h
0x180015780  jnz     short loc_1800157A4
0x180015782  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180015789  mov     [rbp+90h], rax
0x180015790  lea     rdx, [rbp+90h]; union _CLS_LSN *
0x180015797  mov     rcx, [rbp+0D0h]; this
0x18001579e  call    ?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x1800157a3  nop
0x1800157a4  cmp     byte ptr [rbp+80h], 0
0x1800157ab  jz      short loc_1800157CE
0x1800157ad  mov     rcx, [rbp+0D0h]
0x1800157b4  add     rcx, 148h; CriticalSection
0x1800157bb  call    cs:__imp_RtlLeaveCriticalSection
0x1800157c2  nop     dword ptr [rax+rax+00h]
0x1800157c7  mov     byte ptr [rbp+80h], 0
0x1800157ce  cmp     byte ptr [rbp+81h], 0
0x1800157d5  jz      short loc_1800157F8
0x1800157d7  mov     rcx, [rbp+0D0h]
0x1800157de  add     rcx, 120h; CriticalSection
0x1800157e5  call    cs:__imp_RtlLeaveCriticalSection
0x1800157ec  nop     dword ptr [rax+rax+00h]
0x1800157f1  mov     byte ptr [rbp+81h], 0
0x1800157f8  add     rsp, 80h
  ... truncated ...
```
