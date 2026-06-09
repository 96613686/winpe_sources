# CMethodPart::CreateMethod(ushort const *,CWbemObject *,CWbemObject *)

- ea: `0x18002ac20`
- end: `0x18002afe5`
- name: `?CreateMethod@CMethodPart@@IEAAJPEBGPEAVCWbemObject@@1@Z`
- size: `965`
- prototype: `__int64 __fastcall(CMethodPart *this, const unsigned __int16 *, struct CWbemObject *, struct CWbemObject *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002ca70`

## callees

- `0x180021820`
- `0x180021850`
- `0x180021c90`
- `0x1800287d0`
- `0x180029b60`
- `0x18002a1b0`
- `0x18002a290`
- `0x18002aad0`
- `0x18002ac20`
- `0x18002aff0`
- `0x180037120`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002ae11`
- `wbemcomn!GetMemLogObject` at `0x18002ae43`
- `wbemcomn!GetMemLogObject` at `0x18002ae80`
- `wbemcomn!GetMemLogObject` at `0x18002aef7`
- `wbemcomn!GetMemLogObject` at `0x18002af40`
- `wbemcomn!GetMemLogObject` at `0x18002af86`
- `wbemcomn!GetMemLogObject` at `0x18002ae11`
- `wbemcomn!GetMemLogObject` at `0x18002ae43`
- `wbemcomn!GetMemLogObject` at `0x18002ae80`
- `wbemcomn!GetMemLogObject` at `0x18002aef7`
- `wbemcomn!GetMemLogObject` at `0x18002af40`
- `wbemcomn!GetMemLogObject` at `0x18002af86`
- `wbemcomn!IsValidElementName` at `0x18002ac4d`
- `wbemcomn!IsValidElementName` at `0x18002ac4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ae1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ae51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ae90`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002af05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002af4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002af94`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ae1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ae51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ae90`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002af05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002af4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002af94`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMethodPart::CreateMethod(
        CMethodPart *this,
        const unsigned __int16 *a2,
        struct CWbemObject *a3,
        struct CWbemObject *a4)
{
  unsigned int v8; // r13d
  unsigned int v9; // esi
  unsigned int v10; // eax
  _DWORD *v11; // rdx
  unsigned int (__fastcall ***v12)(_QWORD, CMethodPart *, _QWORD); // rcx
  unsigned int v13; // r15d
  unsigned __int8 *Start; // rax
  __int64 v15; // rcx
  CCompressedString *v16; // rax
  unsigned int v17; // r15d
  unsigned __int8 *v18; // rax
  unsigned int v19; // r13d
  CEmbeddedObject *v20; // rax
  unsigned int v21; // esi
  unsigned int v22; // edi
  CEmbeddedObject *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rsi
  CMemoryLog *v27; // rax
  CWbemRefreshingSvc *v28; // rcx
  CMemoryLog *v29; // rax
  __int64 v30; // rdx
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 v35; // [rsp+20h] [rbp-18h]
  unsigned int v36; // [rsp+24h] [rbp-14h] BYREF
  unsigned int v37; // [rsp+28h] [rbp-10h] BYREF
  unsigned int v38; // [rsp+2Ch] [rbp-Ch]

  if ( IsValidElementName(a2, g_IdentifierLimit) )
  {
    v8 = CCompressedString::ComputeNecessarySpace(a2);
    v9 = CEmbeddedObject::EstimateNecessarySpace(a3);
    v10 = CEmbeddedObject::EstimateNecessarySpace(a4);
    v11 = (_DWORD *)*((_QWORD *)this + 1);
    v12 = (unsigned int (__fastcall ***)(_QWORD, CMethodPart *, _QWORD))*((_QWORD *)this + 8);
    v38 = v10;
    v13 = v8 + v9 + v10 + 4;
    if ( (**v12)(v12, this, v13 + *v11 + 24) )
    {
      **((_DWORD **)this + 1) += v13 + 24;
      Start = CFastHeap::GetStart((CMethodPart *)((char *)this + 24));
      MoveBlock<CFastHeap>((char *)this + 24, Start + 24);
      v15 = *((_QWORD *)this + 1);
      v35 = *(_WORD *)(v15 + 4);
      *(_WORD *)(v15 + 4) = v35 + 1;
      CFastHeap::SetAllocatedDataLength((CMethodPart *)((char *)this + 24), v13 + **((_DWORD **)this + 4));
      v36 = 0;
      if ( (unsigned int)CFastHeap::Allocate((CMethodPart *)((char *)this + 24), v8, &v36) )
      {
        v16 = (CCompressedString *)CFastHeap::ResolveHeapPointer((CMethodPart *)((char *)this + 24), v36);
        CCompressedString::SetFromUnicode(v16, a2);
        v37 = 0;
        if ( (unsigned int)CFastHeap::Allocate((CMethodPart *)((char *)this + 24), 4u, &v37) )
        {
          v17 = v37;
          v18 = CFastHeap::ResolveHeapPointer((CMethodPart *)((char *)this + 24), v37);
          v37 = 0;
          *(_DWORD *)v18 = 4;
          if ( (unsigned int)CFastHeap::Allocate((CMethodPart *)((char *)this + 24), v9, &v37) )
          {
            v19 = v37;
            v20 = (CEmbeddedObject *)CFastHeap::ResolveHeapPointer((CMethodPart *)((char *)this + 24), v37);
            CEmbeddedObject::StoreEmbedded(v20, v9, a3);
            v21 = v38;
            v37 = 0;
            if ( (unsigned int)CFastHeap::Allocate((CMethodPart *)((char *)this + 24), v38, &v37) )
            {
              v22 = v37;
              v23 = (CEmbeddedObject *)CFastHeap::ResolveHeapPointer((CMethodPart *)((char *)this + 24), v37);
              CEmbeddedObject::StoreEmbedded(v23, v21, a4);
              v24 = *((_QWORD *)this + 2);
              v25 = 3LL * v35;
              *(_DWORD *)(v24 + 8 * v25) = v36;
              *(_DWORD *)(v24 + 8 * v25 + 12) = v17;
              *(_DWORD *)(v24 + 8 * v25 + 16) = v19;
              *(_DWORD *)(v24 + 8 * v25 + 20) = v22;
              *(_BYTE *)(v24 + 8 * v25 + 4) = 0;
              *(_DWORD *)(v24 + 8 * v25 + 8) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 16LL))(*((_QWORD *)this + 8));
              return 0;
            }
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, -2147217402);
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              return 2147749894LL;
            }
            v30 = 38;
          }
          else
          {
            v33 = GetMemLogObject();
            CMemoryLog::Write(v33, -2147217402);
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              return 2147749894LL;
            }
            v30 = 37;
          }
        }
        else
        {
          v32 = GetMemLogObject();
          CMemoryLog::Write(v32, -2147217402);
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 2147749894LL;
          }
          v30 = 36;
        }
      }
      else
      {
        v29 = GetMemLogObject();
        CMemoryLog::Write(v29, -2147217402);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 2147749894LL;
        }
        v30 = 35;
      }
    }
    else
    {
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, -2147217402);
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749894LL;
      }
      v30 = 34;
    }
    WPP_SF_d(*((_QWORD *)v28 + 2), v30, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids, 2147749894LL);
    return 2147749894LL;
  }
  v31 = GetMemLogObject();
  CMemoryLog::Write(v31, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x18002ac20  mov     [rsp-40h+arg_18], r9
0x18002ac25  push    rbp
0x18002ac26  push    rbx
0x18002ac27  push    rsi
0x18002ac28  push    rdi
0x18002ac29  push    r12
0x18002ac2b  push    r13
0x18002ac2d  push    r14
0x18002ac2f  push    r15
0x18002ac31  mov     rbp, rsp
0x18002ac34  sub     rsp, 38h
0x18002ac38  mov     rdi, rdx
0x18002ac3b  mov     r14, rcx
0x18002ac3e  mov     edx, cs:?g_IdentifierLimit@@3KA; ulong g_IdentifierLimit
0x18002ac44  mov     rcx, rdi
0x18002ac47  mov     rbx, r9
0x18002ac4a  mov     r12, r8
0x18002ac4d  call    cs:__imp_?IsValidElementName@@YAHPEBGK@Z; IsValidElementName(ushort const *,ulong)
0x18002ac53  test    eax, eax
0x18002ac55  jz      loc_18002AE80
0x18002ac5b  mov     rcx, rdi; unsigned __int16 *
0x18002ac5e  call    ?ComputeNecessarySpace@CCompressedString@@SAHPEBG@Z; CCompressedString::ComputeNecessarySpace(ushort const *)
0x18002ac63  mov     rcx, r12; struct CWbemObject *
0x18002ac66  mov     r13d, eax
0x18002ac69  call    ?EstimateNecessarySpace@CEmbeddedObject@@SAKPEAVCWbemObject@@@Z; CEmbeddedObject::EstimateNecessarySpace(CWbemObject *)
0x18002ac6e  mov     rcx, rbx; struct CWbemObject *
0x18002ac71  mov     esi, eax
0x18002ac73  call    ?EstimateNecessarySpace@CEmbeddedObject@@SAKPEAVCWbemObject@@@Z; CEmbeddedObject::EstimateNecessarySpace(CWbemObject *)
0x18002ac78  mov     rdx, [r14+8]
0x18002ac7c  mov     rcx, [r14+40h]
0x18002ac80  mov     [rbp+var_C], eax
0x18002ac83  lea     r15d, [rax+4]
0x18002ac87  mov     r8d, [rdx]
0x18002ac8a  add     r15d, esi
0x18002ac8d  mov     r9, [rcx]
0x18002ac90  add     r8d, 18h
0x18002ac94  add     r15d, r13d
0x18002ac97  mov     rdx, r14
0x18002ac9a  add     r8d, r15d
0x18002ac9d  mov     rax, [r9]
0x18002aca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aca5  test    eax, eax
0x18002aca7  jz      loc_18002AE11
0x18002acad  mov     rcx, [r14+8]
0x18002acb1  lea     eax, [r15+18h]
0x18002acb5  lea     rbx, [r14+18h]
0x18002acb9  add     [rcx], eax
0x18002acbb  mov     rcx, rbx; this
0x18002acbe  call    ?GetStart@CFastHeap@@QEAAPEAEXZ; CFastHeap::GetStart(void)
0x18002acc3  mov     rcx, rbx
0x18002acc6  lea     rdx, [rax+18h]
0x18002acca  call    ??$MoveBlock@VCFastHeap@@@@YAXAEAVCFastHeap@@PEAE@Z; MoveBlock<CFastHeap>(CFastHeap &,uchar *)
0x18002accf  mov     rcx, [r14+8]
0x18002acd3  movzx   eax, word ptr [rcx+4]
0x18002acd7  mov     [rbp+var_18], ax
0x18002acdb  inc     ax
0x18002acde  mov     [rcx+4], ax
0x18002ace2  mov     rcx, rbx; this
0x18002ace5  mov     rax, [r14+20h]
0x18002ace9  mov     edx, [rax]
0x18002aceb  add     edx, r15d; unsigned int
0x18002acee  call    ?SetAllocatedDataLength@CFastHeap@@QEAAXK@Z; CFastHeap::SetAllocatedDataLength(ulong)
0x18002acf3  lea     r8, [rbp+var_14]; unsigned int *
0x18002acf7  mov     [rbp+var_14], 0
0x18002acfe  mov     edx, r13d; unsigned int
0x18002ad01  mov     rcx, rbx; this
0x18002ad04  call    ?Allocate@CFastHeap@@QEAAHKAEFAK@Z; CFastHeap::Allocate(ulong,ulong &)
0x18002ad09  test    eax, eax
0x18002ad0b  jz      loc_18002AE43
0x18002ad11  mov     edx, [rbp+var_14]; unsigned int
0x18002ad14  mov     rcx, rbx; this
0x18002ad17  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18002ad1c  mov     rdx, rdi; unsigned __int16 *
0x18002ad1f  mov     rcx, rax; this
0x18002ad22  call    ?SetFromUnicode@CCompressedString@@QEAAXPEBG@Z; CCompressedString::SetFromUnicode(ushort const *)
0x18002ad27  xor     edi, edi
0x18002ad29  lea     r8, [rbp+var_10]; unsigned int *
0x18002ad2d  mov     rcx, rbx; this
0x18002ad30  mov     [rbp+var_10], edi
0x18002ad33  lea     r13d, [rdi+4]
0x18002ad37  mov     edx, r13d; unsigned int
0x18002ad3a  call    ?Allocate@CFastHeap@@QEAAHKAEFAK@Z; CFastHeap::Allocate(ulong,ulong &)
0x18002ad3f  test    eax, eax
0x18002ad41  jz      loc_18002AEF7
0x18002ad47  mov     r15d, [rbp+var_10]
0x18002ad4b  mov     rcx, rbx; this
0x18002ad4e  mov     edx, r15d; unsigned int
0x18002ad51  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18002ad56  lea     r8, [rbp+var_10]; unsigned int *
0x18002ad5a  mov     [rbp+var_10], edi
0x18002ad5d  mov     edx, esi; unsigned int
0x18002ad5f  mov     rcx, rbx; this
0x18002ad62  mov     [rax], r13d
0x18002ad65  call    ?Allocate@CFastHeap@@QEAAHKAEFAK@Z; CFastHeap::Allocate(ulong,ulong &)
0x18002ad6a  test    eax, eax
0x18002ad6c  jz      loc_18002AF40
0x18002ad72  mov     r13d, [rbp+var_10]
0x18002ad76  mov     rcx, rbx; this
0x18002ad79  mov     edx, r13d; unsigned int
0x18002ad7c  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18002ad81  mov     r8, r12; struct CWbemObject *
0x18002ad84  mov     edx, esi; unsigned int
0x18002ad86  mov     rcx, rax; this
0x18002ad89  call    ?StoreEmbedded@CEmbeddedObject@@QEAAXKPEAVCWbemObject@@@Z; CEmbeddedObject::StoreEmbedded(ulong,CWbemObject *)
0x18002ad8e  mov     esi, [rbp+var_C]
0x18002ad91  lea     r8, [rbp+var_10]; unsigned int *
0x18002ad95  mov     edx, esi; unsigned int
0x18002ad97  mov     [rbp+var_10], edi
0x18002ad9a  mov     rcx, rbx; this
0x18002ad9d  call    ?Allocate@CFastHeap@@QEAAHKAEFAK@Z; CFastHeap::Allocate(ulong,ulong &)
0x18002ada2  test    eax, eax
0x18002ada4  jz      loc_18002AF86
0x18002adaa  mov     edi, [rbp+var_10]
0x18002adad  mov     rcx, rbx; this
0x18002adb0  mov     edx, edi; unsigned int
0x18002adb2  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18002adb7  mov     r8, [rbp+arg_18]; struct CWbemObject *
0x18002adbb  mov     edx, esi; unsigned int
0x18002adbd  mov     rcx, rax; this
0x18002adc0  call    ?StoreEmbedded@CEmbeddedObject@@QEAAXKPEAVCWbemObject@@@Z; CEmbeddedObject::StoreEmbedded(ulong,CWbemObject *)
0x18002adc5  mov     rbx, [r14+10h]
0x18002adc9  movzx   eax, [rbp+var_18]
0x18002adcd  lea     rsi, [rax+rax*2]
0x18002add1  mov     eax, [rbp+var_14]
0x18002add4  mov     [rbx+rsi*8], eax
0x18002add7  mov     [rbx+rsi*8+0Ch], r15d
0x18002addc  mov     [rbx+rsi*8+10h], r13d
0x18002ade1  mov     [rbx+rsi*8+14h], edi
0x18002ade5  mov     byte ptr [rbx+rsi*8+4], 0
0x18002adea  mov     rcx, [r14+40h]
0x18002adee  mov     rax, [rcx]
0x18002adf1  mov     rax, [rax+10h]
0x18002adf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adfa  mov     [rbx+rsi*8+8], eax
0x18002adfe  xor     eax, eax
0x18002ae00  add     rsp, 38h
0x18002ae04  pop     r15
0x18002ae06  pop     r14
0x18002ae08  pop     r13
0x18002ae0a  pop     r12
0x18002ae0c  pop     rdi
0x18002ae0d  pop     rsi
0x18002ae0e  pop     rbx
0x18002ae0f  pop     rbp
0x18002ae10  retn
0x18002ae11  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ae17  mov     rcx, rax
0x18002ae1a  mov     edx, 80041006h
0x18002ae1f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ae25  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae2c  lea     rax, WPP_GLOBAL_Control
0x18002ae33  cmp     rcx, rax
0x18002ae36  jnz     loc_18002AED9
0x18002ae3c  mov     eax, 80041006h
0x18002ae41  jmp     short loc_18002AE00
0x18002ae43  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ae49  mov     rcx, rax
0x18002ae4c  mov     edx, 80041006h
0x18002ae51  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ae57  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae5e  lea     rax, WPP_GLOBAL_Control
0x18002ae65  cmp     rcx, rax
0x18002ae68  jz      short loc_18002AE3C
0x18002ae6a  test    byte ptr [rcx+1Ch], 1
0x18002ae6e  jz      short loc_18002AE3C
0x18002ae70  cmp     byte ptr [rcx+19h], 2
0x18002ae74  jb      short loc_18002AE3C
0x18002ae76  mov     edx, 23h ; '#'
0x18002ae7b  jmp     loc_18002AFCA
0x18002ae80  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ae86  mov     ebx, 80041008h
0x18002ae8b  mov     rcx, rax
0x18002ae8e  mov     edx, ebx
0x18002ae90  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ae96  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae9d  lea     rax, WPP_GLOBAL_Control
0x18002aea4  cmp     rcx, rax
0x18002aea7  jnz     short loc_18002AEB0
0x18002aea9  mov     eax, ebx
0x18002aeab  jmp     loc_18002AE00
0x18002aeb0  test    byte ptr [rcx+1Ch], 1
0x18002aeb4  jz      short loc_18002AEA9
0x18002aeb6  cmp     byte ptr [rcx+19h], 2
0x18002aeba  jb      short loc_18002AEA9
0x18002aebc  mov     rcx, [rcx+10h]
0x18002aec0  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002aec7  mov     edx, 21h ; '!'
0x18002aecc  mov     r9d, 80041008h
0x18002aed2  call    WPP_SF_d
0x18002aed7  jmp     short loc_18002AEA9
0x18002aed9  test    byte ptr [rcx+1Ch], 1
0x18002aedd  jz      loc_18002AE3C
0x18002aee3  cmp     byte ptr [rcx+19h], 2
0x18002aee7  jb      loc_18002AE3C
0x18002aeed  mov     edx, 22h ; '"'
0x18002aef2  jmp     loc_18002AFCA
0x18002aef7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002aefd  mov     rcx, rax
0x18002af00  mov     edx, 80041006h
0x18002af05  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002af0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af12  lea     rax, WPP_GLOBAL_Control
0x18002af19  cmp     rcx, rax
0x18002af1c  jz      loc_18002AE3C
0x18002af22  test    byte ptr [rcx+1Ch], 1
0x18002af26  jz      loc_18002AE3C
0x18002af2c  cmp     byte ptr [rcx+19h], 2
0x18002af30  jb      loc_18002AE3C
0x18002af36  mov     edx, 24h ; '$'
0x18002af3b  jmp     loc_18002AFCA
0x18002af40  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002af46  mov     rcx, rax
0x18002af49  mov     edx, 80041006h
0x18002af4e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002af54  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af5b  lea     rax, WPP_GLOBAL_Control
0x18002af62  cmp     rcx, rax
0x18002af65  jz      loc_18002AE3C
0x18002af6b  test    byte ptr [rcx+1Ch], 1
0x18002af6f  jz      loc_18002AE3C
0x18002af75  cmp     byte ptr [rcx+19h], 2
0x18002af79  jb      loc_18002AE3C
0x18002af7f  mov     edx, 25h ; '%'
0x18002af84  jmp     short loc_18002AFCA
0x18002af86  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002af8c  mov     rcx, rax
0x18002af8f  mov     edx, 80041006h
0x18002af94  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002af9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afa1  lea     rax, WPP_GLOBAL_Control
0x18002afa8  cmp     rcx, rax
0x18002afab  jz      loc_18002AE3C
0x18002afb1  test    byte ptr [rcx+1Ch], 1
0x18002afb5  jz      loc_18002AE3C
0x18002afbb  cmp     byte ptr [rcx+19h], 2
0x18002afbf  jb      loc_18002AE3C
0x18002afc5  mov     edx, 26h ; '&'
0x18002afca  mov     rcx, [rcx+10h]
0x18002afce  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002afd5  mov     r9d, 80041006h
0x18002afdb  call    WPP_SF_d
0x18002afe0  jmp     loc_18002AE3C
```
