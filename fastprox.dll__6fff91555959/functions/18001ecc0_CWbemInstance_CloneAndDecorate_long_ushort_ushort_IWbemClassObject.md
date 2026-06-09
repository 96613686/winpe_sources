# CWbemInstance::CloneAndDecorate(long,ushort *,ushort *,IWbemClassObject * *)

- ea: `0x18001ecc0`
- end: `0x18001f5c6`
- name: `?CloneAndDecorate@CWbemInstance@@UEAAJJPEAG0PEAPEAUIWbemClassObject@@@Z`
- size: `2310`
- prototype: `__int64 __fastcall(CWbemInstance *this, __int64, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180013e80`
- `0x18001d3b0`
- `0x18001e1b0`
- `0x18001ecc0`
- `0x18001f5d0`
- `0x18001f6e0`
- `0x18001f9d0`
- `0x180037120`
- `0x18006fa66`
- `0x18006fa72`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001f18d`
- `wbemcomn!GetMemLogObject` at `0x18001f27b`
- `wbemcomn!GetMemLogObject` at `0x18001f2e8`
- `wbemcomn!GetMemLogObject` at `0x18001f355`
- `wbemcomn!GetMemLogObject` at `0x18001f4d0`
- `wbemcomn!GetMemLogObject` at `0x18001f18d`
- `wbemcomn!GetMemLogObject` at `0x18001f27b`
- `wbemcomn!GetMemLogObject` at `0x18001f2e8`
- `wbemcomn!GetMemLogObject` at `0x18001f355`
- `wbemcomn!GetMemLogObject` at `0x18001f4d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f19b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f289`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f2f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f363`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f4db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f19b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f289`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f2f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f363`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f4db`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001efe2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001efe2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemInstance::CloneAndDecorate(
        CWbemInstance *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IWbemClassObject **a5)
{
  __int64 v8; // r15
  const void *v9; // rdx
  __int64 v10; // r15
  __int64 v11; // rcx
  unsigned int *v12; // rdi
  char *v13; // rdi
  int *v14; // r15
  char *v15; // r15
  _QWORD *v16; // rdi
  CWbemInstance *v17; // r12
  CWbemInstance *v18; // rax
  __int64 v19; // rcx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rax
  int v22; // ecx
  int v23; // r15d
  int v24; // r13d
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // r12d
  int v29; // eax
  int v30; // ecx
  __int64 v31; // rax
  _BYTE *v32; // r8
  _BYTE *v33; // r9
  char v34; // cl
  _BYTE *v35; // rax
  _BYTE *v36; // rdi
  unsigned __int16 v37; // ax
  _BYTE *v38; // rcx
  _BYTE *v39; // rdi
  unsigned __int16 v40; // ax
  _BYTE *v41; // r14
  _BYTE *v42; // rsi
  unsigned int v43; // ecx
  int v44; // r15d
  CWbemInstance *v45; // rax
  CWbemInstance *v46; // rsi
  int v47; // eax
  int v48; // edi
  __int64 result; // rax
  int Length; // edi
  int v51; // edi
  int v52; // edi
  const void *v53; // rdx
  int v54; // ecx
  char *v55; // rax
  int v56; // eax
  CMemoryLog *v57; // rax
  int v58; // eax
  int v59; // eax
  CMemoryLog *v60; // rax
  CMemoryLog *v61; // rax
  CMemoryLog *v62; // rax
  CCompressedString *v63; // rcx
  unsigned __int64 pExceptionObject; // r15
  _BYTE *v65; // r14
  unsigned int v66; // ecx
  int v67; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v69; // rax
  unsigned int v70; // [rsp+30h] [rbp-D8h]
  _BYTE *v71; // [rsp+40h] [rbp-C8h]
  int v72; // [rsp+48h] [rbp-C0h]
  char v73[8]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v74; // [rsp+58h] [rbp-B0h]
  void (__fastcall *v75)(__int64, __int64); // [rsp+60h] [rbp-A8h]
  __int64 v76; // [rsp+68h] [rbp-A0h]
  CCompressedString *v77; // [rsp+70h] [rbp-98h]
  unsigned __int16 *v78; // [rsp+80h] [rbp-88h]
  unsigned __int16 *v79; // [rsp+88h] [rbp-80h]
  unsigned __int16 *v80; // [rsp+90h] [rbp-78h]
  _BYTE *i; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v82; // [rsp+A0h] [rbp-68h]
  __int64 j; // [rsp+A8h] [rbp-60h]
  unsigned __int16 *v84; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v85; // [rsp+B8h] [rbp-50h]
  CWbemInstance *v86; // [rsp+C0h] [rbp-48h]

  try
  {
    v86 = this;
    (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a5 && a3 && a4 )
    {
      if ( (*((_BYTE *)this + 60) & 4) != 0 )
      {
        v8 = *((_QWORD *)this + 27) + 9LL;
        v9 = (const void *)*((_QWORD *)this + 28);
        if ( (const void *)v8 != v9 )
        {
          memmove_0((void *)(*((_QWORD *)this + 27) + 9LL), v9, *((unsigned int *)this + 60));
          v56 = *((_DWORD *)this + 58) - *((_DWORD *)this + 56);
          *((_QWORD *)this + 28) = v8;
          *((_QWORD *)this + 29) = v8 + v56;
        }
        v10 = *((_QWORD *)this + 28) + *((unsigned int *)this + 60);
        v11 = *((_QWORD *)this + 34);
        v12 = (unsigned int *)((char *)this + 264);
        if ( v10 != v11 - 4 )
        {
          memmove_0((void *)(*((_QWORD *)this + 28) + *((unsigned int *)this + 60)), (const void *)(v11 - 4), *v12);
          v11 = v10 + 4;
          *((_QWORD *)this + 34) = v10 + 4;
        }
        v13 = (char *)(v11 + *v12 - 4LL);
        v14 = (int *)((char *)this + 340);
        if ( v13 == *((char **)this + 43) )
        {
          v13 = (char *)*((_QWORD *)this + 43);
        }
        else
        {
          memmove_0(v13, *((const void **)this + 43), *v14);
          *((_QWORD *)this + 43) = v13;
        }
        v15 = &v13[*v14];
        v16 = (_QWORD *)((char *)this + 360);
        v17 = (CWbemInstance *)((char *)this + 376);
        v18 = (CWbemInstance *)*((_QWORD *)this + 46);
        if ( v18 == (CWbemInstance *)((char *)this + 376) )
          v19 = *v16 - 4LL;
        else
          v19 = *((_QWORD *)this + 46);
        if ( v15 != (char *)v19 )
        {
          if ( v18 == v17 )
          {
            v53 = (const void *)(*v16 - 4LL);
            v54 = 0;
          }
          else
          {
            v53 = (const void *)*((_QWORD *)this + 46);
            v54 = 8;
          }
          memmove_0(v15, v53, (unsigned int)(v54 + 4 + *(_DWORD *)v18));
          if ( *((CWbemInstance **)this + 46) == v17 )
          {
            v55 = v15 + 4;
          }
          else
          {
            *((_QWORD *)this + 46) = v15;
            v55 = v15 + 12;
          }
          *v16 = v55;
        }
        CFastHeap::Trim((CWbemInstance *)((char *)this + 360));
        v20 = a3;
        v78 = a3;
        while ( *v20 )
        {
          if ( HIBYTE(*v20) )
          {
            v23 = 0;
            v24 = 2 * CCompressedString::fast_wcslen(a3) + 3;
            goto LABEL_24;
          }
          v78 = ++v20;
        }
        v21 = a3;
        v85 = a3;
        v22 = 0;
        while ( *(_BYTE *)v21 || *((_BYTE *)v21 + 1) )
        {
          v85 = ++v21;
          ++v22;
        }
        v23 = 1;
        v24 = v22 + 2;
LABEL_24:
        v25 = a4;
        v79 = a4;
        while ( *v25 )
        {
          if ( HIBYTE(*v25) )
          {
            v28 = 0;
            v29 = 2 * CCompressedString::fast_wcslen(a4) + 4;
            goto LABEL_33;
          }
          v79 = ++v25;
        }
        v26 = a4;
        v84 = a4;
        v27 = 0;
        while ( *(_BYTE *)v26 || *((_BYTE *)v26 + 1) )
        {
          v84 = ++v26;
          ++v27;
        }
        v28 = 1;
        v29 = v27 + 3;
LABEL_33:
        v72 = v24 + v29;
        if ( (**((_BYTE **)this + 9) & 4) != 0 )
        {
          Length = CCompressedString::GetLength(*((CCompressedString **)this + 11));
          v30 = Length + CCompressedString::GetLength(*((CCompressedString **)this + 10)) + 1;
        }
        else
        {
          v30 = 1;
        }
        v70 = v72 + *((_DWORD *)this + 42) - v30;
        v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 8LL))(*((_QWORD *)this + 15));
        v71 = (_BYTE *)v31;
        if ( v31 )
        {
          MakeObjGuard<CBlobControl,void (CBlobControl::*)(unsigned char *),unsigned char *>(
            v73,
            *((_QWORD *)this + 15),
            v31,
            v31);
          v34 = **((_BYTE **)this + 9);
          *v33 = v34;
          v34 |= 4u;
          *v33 = v34;
          *v33 = v34 & 0xDF;
          v35 = v33 + 1;
          v77 = (CCompressedString *)(v33 + 1);
          v36 = v33 + 2;
          if ( v23 )
          {
            *v35 = 0;
            v80 = a3;
            for ( i = v33 + 2; ; i = v36 )
            {
              v37 = *a3;
              if ( !*a3 )
                break;
              v80 = ++a3;
              *v36++ = v37;
            }
            *v36 = 0;
          }
          else
          {
            *v35 = 1;
            v58 = CCompressedString::fast_wcslen(a3);
            memcpy_0(v36, a3, 2 * v58 + 2);
            v32 = v71;
          }
          v38 = v32 + 1;
          v39 = &v32[v24 + 2];
          if ( v28 )
          {
            v38[v24] = 0;
            v82 = a4;
            for ( j = (__int64)&v32[v24 + 2]; ; j = (__int64)v39 )
            {
              v40 = *a4;
              if ( !*a4 )
                break;
              v82 = ++a4;
              *v39++ = v40;
            }
            *v39 = 0;
          }
          else
          {
            v38[v24] = 1;
            v59 = CCompressedString::fast_wcslen(a4);
            memcpy_0(v39, a4, 2 * v59 + 2);
            v32 = v71;
          }
          v41 = &v32[v72];
          v42 = (_BYTE *)*((_QWORD *)this + 9);
          if ( (*v42 & 4) != 0 )
          {
            v51 = CCompressedString::GetLength(*((CCompressedString **)this + 11));
            v44 = v51 + CCompressedString::GetLength(*((CCompressedString **)this + 10)) + 1;
            v52 = CCompressedString::GetLength(*((CCompressedString **)this + 11));
            v43 = v52 + CCompressedString::GetLength(*((CCompressedString **)this + 10)) + 1;
          }
          else
          {
            v43 = 1;
            v44 = 1;
          }
          memcpy_0(v41, &v42[v43], (unsigned int)(*((_DWORD *)this + 42) - v44));
          v45 = (CWbemInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
          if ( v45 )
            v46 = CWbemInstance::CWbemInstance(v45);
          else
            v46 = 0;
          if ( v46 )
          {
            v47 = *((_DWORD *)this + 15);
            if ( (v47 & 4) != 0 )
            {
              if ( (v47 & 8) != 0 )
              {
                v73[0] = 1;
                (*(void (__fastcall **)(CWbemInstance *, _BYTE *, _QWORD))(*(_QWORD *)v46 + 1152LL))(v46, v71, v70);
              }
              else if ( (v47 & 0x10) != 0 )
              {
                v73[0] = 1;
                *((_QWORD *)v46 + 9) = v71;
                if ( (*v71 & 4) != 0 )
                {
                  *((_QWORD *)v46 + 10) = v71 + 1;
                  v63 = (CCompressedString *)&v71[(int)CCompressedString::GetLength((CCompressedString *)(v71 + 1)) + 1];
                  *((_QWORD *)v46 + 11) = v63;
                }
                else
                {
                  *((_QWORD *)v46 + 11) = 0;
                  *((_QWORD *)v46 + 10) = 0;
                  v63 = 0;
                  v77 = 0;
                }
                pExceptionObject = **((int **)this + 27);
                v65 = (_BYTE *)*((_QWORD *)v46 + 9);
                if ( (*v65 & 4) != 0 )
                {
                  v67 = CCompressedString::GetLength(v63);
                  v66 = v67 + CCompressedString::GetLength(v77) + 1;
                }
                else
                {
                  v66 = 1;
                }
                CInstancePart::SetData(
                  (CWbemInstance *)((char *)v46 + 176),
                  &v65[v66],
                  (CWbemInstance *)((char *)v46 + 152),
                  (CWbemInstance *)((char *)this + 400),
                  pExceptionObject);
                *((_DWORD *)v46 + 15) = 3;
                v48 = (*(__int64 (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)v46 + 592LL))(
                        v46,
                        *((_QWORD *)this + 8));
                if ( v48 < 0 )
                {
                  (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)v46 + 848LL))(v46, 1);
                  MemLogObject = GetMemLogObject();
                  CMemoryLog::Write(MemLogObject, v48);
                  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      53,
                      WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                      (unsigned int)v48);
                  }
                  if ( !v73[0] )
                    v75(v74, v76);
                  goto LABEL_54;
                }
                *((_DWORD *)v46 + 15) = *((_DWORD *)this + 15);
                *((_DWORD *)v46 + 42) = v70;
              }
            }
            (*(void (__fastcall **)(CWbemInstance *))(*(_QWORD *)v46 + 1128LL))(v46);
            *((_DWORD *)v46 + 10) = 0;
            v48 = (**(__int64 (__fastcall ***)(CWbemInstance *, GUID *, struct IWbemClassObject **))v46)(
                    v46,
                    &IID_IWbemClassObject,
                    a5);
            if ( !v73[0] )
              v75(v74, v76);
LABEL_54:
            (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return (unsigned int)v48;
          }
          v62 = GetMemLogObject();
          CMemoryLog::Write(v62, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749894LL);
          }
          if ( !v73[0] )
            v75(v74, v76);
          (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          result = 2147749894LL;
        }
        else
        {
          v61 = GetMemLogObject();
          CMemoryLog::Write(v61, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749894LL);
          }
          (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          result = 2147749894LL;
        }
      }
      else
      {
        v60 = GetMemLogObject();
        CMemoryLog::Write(v60, -2147217386);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749910LL);
        }
        (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        result = 2147749910LL;
      }
    }
    else
    {
      v57 = GetMemLogObject();
      CMemoryLog::Write(v57, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v69 = GetMemLogObject();
    CMemoryLog::Write(v69, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v86 = this;
}

```

## disassembly

```asm
0x18001ecc0  push    rbx
0x18001ecc2  push    rsi
0x18001ecc3  push    rdi
0x18001ecc4  push    r12
0x18001ecc6  push    r13
0x18001ecc8  push    r14
0x18001ecca  push    r15
0x18001eccc  sub     rsp, 0D0h
0x18001ecd3  mov     rsi, r9
0x18001ecd6  mov     r14, r8
0x18001ecd9  mov     rbx, rcx
0x18001ecdc  xor     r13d, r13d
0x18001ecdf  mov     [rsp+108h+var_48], rcx
0x18001ece7  mov     rax, [rcx]
0x18001ecea  mov     edx, 1
0x18001ecef  mov     rax, [rax+118h]
0x18001ecf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecfb  nop
0x18001ecfc  cmp     [rsp+108h+arg_20], r13
0x18001ed04  jz      loc_18001F18D
0x18001ed0a  test    r14, r14
0x18001ed0d  jz      loc_18001F18D
0x18001ed13  test    rsi, rsi
0x18001ed16  jz      loc_18001F18D
0x18001ed1c  test    byte ptr [rbx+3Ch], 4
0x18001ed20  jz      loc_18001F27B
0x18001ed26  mov     r15, [rbx+0D8h]
0x18001ed2d  add     r15, 9
0x18001ed31  mov     rdx, [rbx+0E0h]; Src
0x18001ed38  cmp     r15, rdx
0x18001ed3b  jnz     loc_18001F12B
0x18001ed41  mov     r15d, [rbx+0F0h]
0x18001ed48  add     r15, [rbx+0E0h]
0x18001ed4f  mov     rcx, [rbx+110h]
0x18001ed56  lea     rdx, [rcx-4]; Src
0x18001ed5a  lea     rdi, [rbx+108h]
0x18001ed61  cmp     r15, rdx
0x18001ed64  jnz     loc_18001F172
0x18001ed6a  mov     edi, [rdi]
0x18001ed6c  add     rdi, 0FFFFFFFFFFFFFFFCh
0x18001ed70  add     rdi, rcx
0x18001ed73  mov     rax, [rbx+158h]
0x18001ed7a  lea     r15, [rbx+154h]
0x18001ed81  cmp     rdi, rax
0x18001ed84  jnz     loc_18001F22B
0x18001ed8a  mov     rdi, rax
0x18001ed8d  movsxd  r15, dword ptr [r15]
0x18001ed90  add     r15, rdi
0x18001ed93  lea     rdi, [rbx+168h]
0x18001ed9a  lea     r12, [rdi+10h]
0x18001ed9e  mov     rax, [rdi+8]
0x18001eda2  cmp     rax, r12
0x18001eda5  jnz     loc_18001F081
0x18001edab  mov     rcx, [rdi]
0x18001edae  sub     rcx, 4
0x18001edb2  cmp     r15, rcx
0x18001edb5  jnz     loc_18001F0F9
0x18001edbb  mov     rcx, rdi; this
0x18001edbe  call    ?Trim@CFastHeap@@QEAAXXZ; CFastHeap::Trim(void)
0x18001edc3  mov     rax, r14
0x18001edc6  mov     [rsp+108h+var_88], rax
0x18001edce  movzx   ecx, word ptr [rax]
0x18001edd1  test    cx, cx
0x18001edd4  jz      short loc_18001EDF0
0x18001edd6  shr     cx, 8
0x18001edda  test    cl, cl
0x18001eddc  jnz     loc_18001F24C
0x18001ede2  add     rax, 2
0x18001ede6  mov     [rsp+108h+var_88], rax
0x18001edee  jmp     short loc_18001EDCE
0x18001edf0  mov     rax, r14
0x18001edf3  mov     [rsp+108h+var_50], rax
0x18001edfb  mov     [rsp+108h+var_D0], r13d
0x18001ee00  mov     ecx, r13d
0x18001ee03  mov     [rsp+108h+var_D0], ecx
0x18001ee07  cmp     byte ptr [rax], 0
0x18001ee0a  jz      short loc_18001EE1C
0x18001ee0c  add     rax, 2
0x18001ee10  mov     [rsp+108h+var_50], rax
0x18001ee18  inc     ecx
0x18001ee1a  jmp     short loc_18001EE03
0x18001ee1c  cmp     byte ptr [rax+1], 0
0x18001ee20  jnz     short loc_18001EE0C
0x18001ee22  mov     r15d, 1
0x18001ee28  lea     r13d, [rcx+2]
0x18001ee2c  mov     rax, rsi
0x18001ee2f  mov     [rsp+108h+var_80], rax
0x18001ee37  movzx   ecx, word ptr [rax]
0x18001ee3a  test    cx, cx
0x18001ee3d  jz      short loc_18001EE59
0x18001ee3f  shr     cx, 8
0x18001ee43  test    cl, cl
0x18001ee45  jnz     loc_18001F264
0x18001ee4b  add     rax, 2
0x18001ee4f  mov     [rsp+108h+var_80], rax
0x18001ee57  jmp     short loc_18001EE37
0x18001ee59  mov     rax, rsi
0x18001ee5c  mov     [rsp+108h+var_58], rax
0x18001ee64  mov     [rsp+108h+var_D4], 0
0x18001ee6c  xor     ecx, ecx
0x18001ee6e  mov     [rsp+108h+var_D4], ecx
0x18001ee72  cmp     byte ptr [rax], 0
0x18001ee75  jz      short loc_18001EE87
0x18001ee77  add     rax, 2
0x18001ee7b  mov     [rsp+108h+var_58], rax
0x18001ee83  inc     ecx
0x18001ee85  jmp     short loc_18001EE6E
0x18001ee87  cmp     byte ptr [rax+1], 0
0x18001ee8b  jnz     short loc_18001EE77
0x18001ee8d  mov     r12d, 1
0x18001ee93  lea     eax, [rcx+3]
0x18001ee96  add     eax, r13d
0x18001ee99  mov     dword ptr [rsp+108h+var_C0], eax
0x18001ee9d  mov     rax, [rbx+48h]
0x18001eea1  test    byte ptr [rax], 4
0x18001eea4  jnz     loc_18001F089
0x18001eeaa  mov     ecx, 1
0x18001eeaf  mov     edx, [rbx+0A8h]
0x18001eeb5  sub     edx, ecx
0x18001eeb7  add     edx, dword ptr [rsp+108h+var_C0]
0x18001eebb  mov     [rsp+108h+var_D8], edx
0x18001eebf  mov     rcx, [rbx+78h]
0x18001eec3  mov     rax, [rcx]
0x18001eec6  mov     rax, [rax+8]
0x18001eeca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eecf  mov     r8, rax
0x18001eed2  mov     [rsp+108h+var_C8], rax
0x18001eed7  test    rax, rax
0x18001eeda  jz      loc_18001F2E8
0x18001eee0  mov     r9, rax
0x18001eee3  mov     rdx, [rbx+78h]
0x18001eee7  lea     rcx, [rsp+108h+var_B8]
0x18001eeec  call    ??$MakeObjGuard@VCBlobControl@@P81@EAAXPEAE@ZPEAE@@YA?AV?$ObjScopeGuardImpl1@VCBlobControl@@P81@EAAXPEAE@ZPEAE@@AEAVCBlobControl@@P81@EAAXPEAE@Z1@Z; MakeObjGuard<CBlobControl,void (CBlobControl::*)(uchar *),uchar *>(CBlobControl &,void (CBlobControl::*)(uchar *),uchar *)
0x18001eef1  nop
0x18001eef2  mov     rax, [rbx+48h]
0x18001eef6  movzx   ecx, byte ptr [rax]
0x18001eef9  mov     [r9], cl
0x18001eefc  or      cl, 4
0x18001eeff  mov     [r9], cl
0x18001ef02  and     cl, 0DFh
0x18001ef05  mov     [r9], cl
0x18001ef08  lea     rax, [r9+1]
0x18001ef0c  mov     [rsp+108h+var_98], rax
0x18001ef11  lea     rdi, [rax+1]
0x18001ef15  test    r15d, r15d
0x18001ef18  jz      loc_18001F1D6
0x18001ef1e  mov     byte ptr [rax], 0
0x18001ef21  mov     [rsp+108h+var_78], r14
0x18001ef29  mov     [rsp+108h+var_70], rdi
0x18001ef31  movzx   eax, word ptr [r14]
0x18001ef35  test    ax, ax
0x18001ef38  jz      short loc_18001EF55
0x18001ef3a  add     r14, 2
0x18001ef3e  mov     [rsp+108h+var_78], r14
0x18001ef46  mov     [rdi], al
0x18001ef48  inc     rdi
0x18001ef4b  mov     [rsp+108h+var_70], rdi
0x18001ef53  jmp     short loc_18001EF31
0x18001ef55  mov     byte ptr [rdi], 0
0x18001ef58  movsxd  rax, r13d
0x18001ef5b  lea     rcx, [r8+1]
0x18001ef5f  lea     rdi, [rax+1]
0x18001ef63  add     rdi, rcx
0x18001ef66  test    r12d, r12d
0x18001ef69  jz      loc_18001F200
0x18001ef6f  mov     byte ptr [rcx+rax], 0
0x18001ef73  mov     [rsp+108h+var_68], rsi
0x18001ef7b  mov     [rsp+108h+var_60], rdi
0x18001ef83  movzx   eax, word ptr [rsi]
0x18001ef86  test    ax, ax
0x18001ef89  jz      short loc_18001EFA6
0x18001ef8b  add     rsi, 2
0x18001ef8f  mov     [rsp+108h+var_68], rsi
0x18001ef97  mov     [rdi], al
0x18001ef99  inc     rdi
0x18001ef9c  mov     [rsp+108h+var_60], rdi
0x18001efa4  jmp     short loc_18001EF83
0x18001efa6  mov     byte ptr [rdi], 0
0x18001efa9  movsxd  r14, dword ptr [rsp+108h+var_C0]
0x18001efae  add     r14, r8
0x18001efb1  mov     rsi, [rbx+48h]
0x18001efb5  test    byte ptr [rsi], 4
0x18001efb8  jnz     loc_18001F0A7
0x18001efbe  mov     ecx, 1
0x18001efc3  mov     r15d, ecx
0x18001efc6  mov     r8d, [rbx+0A8h]
0x18001efcd  sub     r8d, r15d; Size
0x18001efd0  mov     edx, ecx
0x18001efd2  add     rdx, rsi; Src
0x18001efd5  mov     rcx, r14; void *
0x18001efd8  call    memcpy_0
0x18001efdd  mov     ecx, 2A0h
0x18001efe2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001efe8  mov     [rsp+108h+var_C0], rax
0x18001efed  test    rax, rax
0x18001eff0  jz      loc_18001F245
0x18001eff6  mov     rcx, rax; this
0x18001eff9  call    ??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x18001effe  mov     rsi, rax
0x18001f001  test    rsi, rsi
0x18001f004  jz      loc_18001F355
0x18001f00a  mov     eax, [rbx+3Ch]
0x18001f00d  test    al, 4
0x18001f00f  jnz     loc_18001F551
0x18001f015  mov     rax, [rsi]
0x18001f018  mov     rcx, rsi
0x18001f01b  mov     rax, [rax+468h]
0x18001f022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f027  mov     dword ptr [rsi+28h], 0
0x18001f02e  mov     rax, [rsi]
0x18001f031  mov     r8, [rsp+108h+arg_20]
0x18001f039  lea     rdx, IID_IWbemClassObject
0x18001f040  mov     rcx, rsi
0x18001f043  mov     rax, [rax]
0x18001f046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f04b  mov     edi, eax
0x18001f04d  cmp     [rsp+108h+var_B8], 0
0x18001f052  jz      loc_18001F0E0
0x18001f058  mov     rax, [rbx]
0x18001f05b  xor     edx, edx
0x18001f05d  mov     rcx, rbx
0x18001f060  mov     rax, [rax+120h]
0x18001f067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f06c  mov     eax, edi
0x18001f06e  add     rsp, 0D0h
0x18001f075  pop     r15
0x18001f077  pop     r14
0x18001f079  pop     r13
0x18001f07b  pop     r12
0x18001f07d  pop     rdi
0x18001f07e  pop     rsi
0x18001f07f  pop     rbx
0x18001f080  retn
0x18001f081  mov     rcx, rax
0x18001f084  jmp     loc_18001EDB2
0x18001f089  mov     rcx, [rbx+58h]; this
0x18001f08d  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x18001f092  mov     edi, eax
0x18001f094  mov     rcx, [rbx+50h]; this
0x18001f098  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x18001f09d  lea     ecx, [rax+1]
0x18001f0a0  add     ecx, edi
0x18001f0a2  jmp     loc_18001EEAF
0x18001f0a7  mov     rcx, [rbx+58h]; this
0x18001f0ab  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x18001f0b0  mov     edi, eax
0x18001f0b2  mov     rcx, [rbx+50h]; this
0x18001f0b6  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x18001f0bb  lea     r15d, [rax+1]
0x18001f0bf  add     r15d, edi
0x18001f0c2  mov     rcx, [rbx+58h]; this
0x18001f0c6  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x18001f0cb  mov     edi, eax
0x18001f0cd  mov     rcx, [rbx+50h]; this
0x18001f0d1  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x18001f0d6  lea     ecx, [rax+1]
0x18001f0d9  add     ecx, edi
0x18001f0db  jmp     loc_18001EFC6
0x18001f0e0  mov     rdx, [rsp+108h+var_A0]
0x18001f0e5  mov     rcx, [rsp+108h+var_B0]
0x18001f0ea  mov     rax, [rsp+108h+var_A8]
0x18001f0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0f4  jmp     loc_18001F058
0x18001f0f9  mov     r8d, [rax]
0x18001f0fc  cmp     rax, r12
0x18001f0ff  jnz     short loc_18001F168
0x18001f101  mov     rdx, [rdi]
0x18001f104  sub     rdx, 4; Src
0x18001f108  mov     ecx, r13d
0x18001f10b  add     ecx, 4
0x18001f10e  add     r8d, ecx; Size
0x18001f111  mov     rcx, r15; void *
0x18001f114  call    memmove_0
0x18001f119  cmp     [rdi+8], r12
0x18001f11d  jnz     short loc_18001F15E
0x18001f11f  lea     rax, [r15+4]
0x18001f123  mov     [rdi], rax
0x18001f126  jmp     loc_18001EDBB
0x18001f12b  mov     r8d, [rbx+0F0h]; Size
0x18001f132  mov     rcx, r15; void *
0x18001f135  call    memmove_0
0x18001f13a  mov     eax, [rbx+0E8h]
0x18001f140  sub     eax, [rbx+0E0h]
0x18001f146  mov     [rbx+0E0h], r15
0x18001f14d  cdqe
0x18001f14f  add     rax, r15
0x18001f152  mov     [rbx+0E8h], rax
0x18001f159  jmp     loc_18001ED41
0x18001f15e  mov     [rdi+8], r15
0x18001f162  lea     rax, [r15+0Ch]
0x18001f166  jmp     short loc_18001F123
0x18001f168  mov     rdx, rax
0x18001f16b  mov     ecx, 8
0x18001f170  jmp     short loc_18001F10B
0x18001f172  mov     r8d, [rdi]; Size
0x18001f175  mov     rcx, r15; void *
0x18001f178  call    memmove_0
0x18001f17d  lea     rcx, [r15+4]
0x18001f181  mov     [rbx+110h], rcx
0x18001f188  jmp     loc_18001ED6A
  ... truncated ...
```
