# CWbemObjectArrayPacket::MarshalPacket(long,IWbemClassObject * *,_GUID *,int *)

- ea: `0x18003a890`
- end: `0x18003af6e`
- name: `?MarshalPacket@CWbemObjectArrayPacket@@QEAAJJPEAPEAUIWbemClassObject@@PEAU_GUID@@PEAH@Z`
- size: `1758`
- prototype: `__int64 __fastcall(CWbemObjectArrayPacket *__hidden this, int, struct IWbemClassObject **, struct _GUID *, int *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003a690`
- `0x18003bf40`
- `0x18005c2cc`
- `0x180083310`
- `0x1800833f0`

## callees

- `0x180035b08`
- `0x180037120`
- `0x18003a890`
- `0x18003af74`
- `0x18003c1e0`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003ad0c`
- `wbemcomn!GetMemLogObject` at `0x18003ad8b`
- `wbemcomn!GetMemLogObject` at `0x18003ada1`
- `wbemcomn!GetMemLogObject` at `0x18003adb7`
- `wbemcomn!GetMemLogObject` at `0x18003ae1e`
- `wbemcomn!GetMemLogObject` at `0x18003ae85`
- `wbemcomn!GetMemLogObject` at `0x18003aeec`
- `wbemcomn!GetMemLogObject` at `0x18003af58`
- `wbemcomn!GetMemLogObject` at `0x18003ad0c`
- `wbemcomn!GetMemLogObject` at `0x18003ad8b`
- `wbemcomn!GetMemLogObject` at `0x18003ada1`
- `wbemcomn!GetMemLogObject` at `0x18003adb7`
- `wbemcomn!GetMemLogObject` at `0x18003ae1e`
- `wbemcomn!GetMemLogObject` at `0x18003ae85`
- `wbemcomn!GetMemLogObject` at `0x18003aeec`
- `wbemcomn!GetMemLogObject` at `0x18003af58`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ad17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ad96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003adac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003adc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003aefa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af63`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ad17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ad96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003adac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003adc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ae93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003aefa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003af63`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemObjectArrayPacket::MarshalPacket(
        CWbemObjectArrayPacket *this,
        int a2,
        struct IWbemClassObject **a3,
        struct _GUID *a4,
        int *a5)
{
  struct _GUID *v5; // r13
  int v7; // ebx
  unsigned int *v8; // rax
  __int64 v9; // rcx
  int v10; // r15d
  unsigned int v11; // r14d
  unsigned __int8 *v12; // rsi
  unsigned int v13; // r15d
  int v14; // edi
  struct IWbemClassObject **v15; // rbx
  struct IWbemClassObject *v16; // r13
  int v17; // eax
  unsigned int v18; // ebx
  unsigned __int8 v19; // r9
  unsigned __int8 *v20; // r8
  unsigned __int8 *v21; // r8
  CWbemRefreshingSvc *v22; // rcx
  _DWORD *v23; // r12
  struct IWbemClassObject *v24; // r13
  int v25; // eax
  __int64 v26; // rdx
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v36; // [rsp+30h] [rbp-71h] BYREF
  int v37; // [rsp+34h] [rbp-6Dh] BYREF
  void **v38; // [rsp+38h] [rbp-69h] BYREF
  unsigned __int8 *v39; // [rsp+40h] [rbp-61h]
  unsigned int v40; // [rsp+48h] [rbp-59h]
  unsigned __int8 *v41; // [rsp+50h] [rbp-51h]
  unsigned int v42; // [rsp+58h] [rbp-49h]
  __int64 v43; // [rsp+60h] [rbp-41h]
  unsigned __int8 *v44; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-31h]
  unsigned __int8 *v46; // [rsp+78h] [rbp-29h]
  unsigned int v47; // [rsp+80h] [rbp-21h]
  _QWORD v48[2]; // [rsp+88h] [rbp-19h] BYREF
  int v49; // [rsp+98h] [rbp-9h]
  __int64 v50; // [rsp+A0h] [rbp-1h]
  int v51; // [rsp+A8h] [rbp+7h]
  unsigned int pExceptionObject; // [rsp+100h] [rbp+5Fh] BYREF
  int v53; // [rsp+108h] [rbp+67h]
  struct IWbemClassObject **v54; // [rsp+110h] [rbp+6Fh]
  struct _GUID *v55; // [rsp+118h] [rbp+77h]

  v55 = a4;
  v54 = a3;
  v53 = a2;
  v5 = a4;
  if ( !*(_QWORD *)this )
  {
    v7 = -2147217386;
    goto LABEL_79;
  }
  v7 = 0;
  **(_DWORD **)this = 12;
  *(_DWORD *)(*(_QWORD *)this + 4LL) = *((_DWORD *)this + 2) - 12;
  *(_DWORD *)(*(_QWORD *)this + 8LL) = a2;
  if ( a2 > 0 )
  {
    v8 = *(unsigned int **)this;
    v9 = **(unsigned int **)this;
    v10 = *((_DWORD *)this + 2);
    v11 = 0;
    v36 = 0;
    v46 = 0;
    v47 = 0;
    v44 = 0;
    v45 = 0;
    v48[0] = &CWbemInstancePacket::`vftable';
    v50 = 0;
    v51 = 0;
    v48[1] = 0;
    v49 = 0;
    v41 = 0;
    v42 = 0;
    v39 = 0;
    v40 = 0;
    v38 = &CWbemClasslessInstancePacket::`vftable';
    v12 = (unsigned __int8 *)v8 + v9;
    v13 = v10 - v9;
    v43 = 0;
    v14 = 0;
    while ( 1 )
    {
      if ( v14 >= a2 )
      {
LABEL_38:
        v38 = &CWbemInstancePacket::`vftable';
        v48[0] = &CWbemInstancePacket::`vftable';
        if ( v7 >= 0 )
          goto LABEL_39;
LABEL_79:
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v7);
        goto LABEL_39;
      }
      v15 = &a3[v14];
      if ( ((unsigned int (__fastcall *)(struct IWbemClassObject *))(*v15)->lpVtbl[2].DeleteMethod)(*v15) )
        break;
      if ( !a5[v14] )
      {
        if ( v12 )
        {
          if ( v12 + 9 < v12 )
          {
            v32 = GetMemLogObject();
            CMemoryLog::Write(v32, -2);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
                "SafeIntException(ERROR_INVALID_PARAMETER)");
            }
            pExceptionObject = 87;
            throw (SafeIntException *)&pExceptionObject;
          }
          v41 = v12 + 9;
          if ( v13 < 0x21 )
          {
            v31 = GetMemLogObject();
            CMemoryLog::Write(v31, -2);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
                "SafeIntException(ERROR_INVALID_PARAMETER)");
            }
            pExceptionObject = 87;
            throw (SafeIntException *)&pExceptionObject;
          }
          v42 = v13 - 9;
        }
        else
        {
          v41 = 0;
          v42 = 0;
        }
        v39 = v12;
        v40 = v13;
        v16 = *v15;
        pExceptionObject = 0;
        v17 = ((__int64 (__fastcall *)(void ***, struct IWbemClassObject *, _QWORD, _QWORD, unsigned int *))v38[1])(
                &v38,
                v16,
                0,
                0,
                &pExceptionObject);
        v7 = v17;
        if ( v17 < 0 )
        {
          if ( v17 != -2147217348 )
            goto LABEL_56;
          v18 = pExceptionObject + 24;
          v19 = ((__int64 (__fastcall *)(void ***))*v38)(&v38);
          v20 = v39;
          if ( v39 )
          {
            if ( v40 >= (unsigned __int64)v18 + 9 )
            {
              *(_QWORD *)v39 = 0;
              v20[8] = 0;
              *(_DWORD *)v39 = 9;
              *((_DWORD *)v39 + 1) = v18;
              v39[8] = v19;
              v7 = 0;
LABEL_16:
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
                  (unsigned int)v7);
              }
              if ( v7 >= 0 )
              {
                v21 = v41;
                *(_DWORD *)v41 = 24;
                *((_DWORD *)v41 + 1) = pExceptionObject;
                *(struct _GUID *)(v41 + 8) = v55[v14];
                v37 = 0;
                v7 = ((__int64 (__fastcall *)(void ***, struct IWbemClassObject *, unsigned __int8 *, _QWORD, int *))v38[1])(
                       &v38,
                       v16,
                       v21 + 24,
                       pExceptionObject,
                       &v37);
                if ( v7 >= 0 )
                {
                  v11 = pExceptionObject + 33;
                  v36 = pExceptionObject + 33;
                  goto LABEL_21;
                }
              }
LABEL_56:
              v29 = GetMemLogObject();
              CMemoryLog::Write(v29, v7);
              goto LABEL_21;
            }
            v7 = -2147217348;
          }
          else
          {
            v7 = -2147217400;
          }
          v28 = GetMemLogObject();
          CMemoryLog::Write(v28, v7);
          goto LABEL_16;
        }
LABEL_21:
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = 25;
LABEL_37:
          WPP_SF_d(*((_QWORD *)v22 + 2), v26, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, (unsigned int)v7);
        }
        goto LABEL_23;
      }
      v7 = CWbemInstancePacket::WriteToPacket((CWbemInstancePacket *)v48, v12, v13, *v15, &v5[v14], &v36);
      v11 = v36;
LABEL_24:
      if ( v7 < 0 )
        goto LABEL_38;
      ++v14;
      v12 += v11;
      v13 -= v11;
      a2 = v53;
      a3 = v54;
    }
    if ( v12 )
    {
      v23 = v12 + 9;
      if ( v12 + 9 < v12 )
      {
        v34 = GetMemLogObject();
        CMemoryLog::Write(v34, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        pExceptionObject = 87;
        throw (SafeIntException *)&pExceptionObject;
      }
      v46 = v12 + 9;
      if ( v13 < 0x11 )
      {
        v33 = GetMemLogObject();
        CMemoryLog::Write(v33, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        pExceptionObject = 87;
        throw (SafeIntException *)&pExceptionObject;
      }
      v47 = v13 - 9;
    }
    else
    {
      v23 = 0;
      v46 = 0;
      v47 = 0;
    }
    v44 = v12;
    v45 = v13;
    v24 = *v15;
    pExceptionObject = 0;
    v25 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, _QWORD, unsigned int *))v24->lpVtbl[2].SpawnInstance)(
            v24,
            0,
            0,
            &pExceptionObject);
    v7 = v25;
    if ( v25 < 0 )
    {
      if ( v25 == -2147217348
        && (v7 = CWbemObjectPacket::SetupObjectPacketHeader((CWbemObjectPacket *)&v44, pExceptionObject + 8, 1u), v7 >= 0)
        && (*v23 = 8,
            v23[1] = pExceptionObject,
            v37 = 0,
            v7 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _DWORD *, _QWORD, int *))v24->lpVtbl[2].SpawnInstance)(
                   v24,
                   v23 + 2,
                   pExceptionObject,
                   &v37),
            v7 >= 0) )
      {
        v11 = pExceptionObject + 17;
        v36 = pExceptionObject + 17;
      }
      else
      {
        v30 = GetMemLogObject();
        CMemoryLog::Write(v30, v7);
      }
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = 16;
      goto LABEL_37;
    }
LABEL_23:
    v5 = v55;
    goto LABEL_24;
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003a890  mov     [rsp-8+arg_18], r9
0x18003a895  mov     [rsp-8+arg_10], r8
0x18003a89a  mov     [rsp-8+arg_8], edx
0x18003a89e  push    rbp
0x18003a89f  push    rbx
0x18003a8a0  push    rsi
0x18003a8a1  push    rdi
0x18003a8a2  push    r12
0x18003a8a4  push    r13
0x18003a8a6  push    r14
0x18003a8a8  push    r15
0x18003a8aa  lea     rbp, [rsp-17h]
0x18003a8af  sub     rsp, 0B8h
0x18003a8b6  mov     r13, r9
0x18003a8b9  mov     r15, rcx
0x18003a8bc  mov     rax, [rcx]
0x18003a8bf  lea     r12, WPP_GLOBAL_Control
0x18003a8c6  test    rax, rax
0x18003a8c9  jz      loc_18003AF53
0x18003a8cf  xor     r10d, r10d
0x18003a8d2  mov     ebx, r10d
0x18003a8d5  mov     dword ptr [rax], 0Ch
0x18003a8db  mov     r9d, [rcx+8]
0x18003a8df  sub     r9d, 0Ch
0x18003a8e3  mov     rax, [rcx]
0x18003a8e6  mov     [rax+4], r9d
0x18003a8ea  mov     rax, [rcx]
0x18003a8ed  mov     [rax+8], edx
0x18003a8f0  test    edx, edx
0x18003a8f2  jle     loc_18003AC72
0x18003a8f8  mov     rax, [rcx]
0x18003a8fb  mov     ecx, [rax]
0x18003a8fd  mov     r15d, [r15+8]
0x18003a901  mov     r14d, r10d
0x18003a904  mov     [rbp+4Fh+var_C0], r10d
0x18003a908  mov     [rbp+4Fh+var_78], r10
0x18003a90c  mov     [rbp+4Fh+var_70], r10d
0x18003a910  mov     [rbp+4Fh+var_88], r10
0x18003a914  mov     [rbp+4Fh+var_80], r10d
0x18003a918  mov     [rbp+4Fh+var_60], r10
0x18003a91c  mov     [rbp+4Fh+var_58], r10d
0x18003a920  lea     r9, ??_7CWbemInstancePacket@@6B@; const CWbemInstancePacket::`vftable'
0x18003a927  mov     [rbp+4Fh+var_68], r9
0x18003a92b  mov     [rbp+4Fh+var_50], r10
0x18003a92f  mov     [rbp+4Fh+var_48], r10d
0x18003a933  mov     [rbp+4Fh+var_60], r10
0x18003a937  mov     [rbp+4Fh+var_58], r10d
0x18003a93b  mov     [rbp+4Fh+var_B0], r10
0x18003a93f  mov     [rbp+4Fh+var_A8], r10d
0x18003a943  mov     [rbp+4Fh+var_B8], r9
0x18003a947  mov     [rbp+4Fh+var_A0], r10
0x18003a94b  mov     [rbp+4Fh+var_98], r10d
0x18003a94f  mov     [rbp+4Fh+var_B0], r10
0x18003a953  mov     [rbp+4Fh+var_A8], r10d
0x18003a957  lea     r9, ??_7CWbemClasslessInstancePacket@@6B@; const CWbemClasslessInstancePacket::`vftable'
0x18003a95e  mov     [rbp+4Fh+var_B8], r9
0x18003a962  lea     rsi, [rax+rcx]
0x18003a966  sub     r15d, ecx
0x18003a969  mov     [rbp+4Fh+var_90], r10
0x18003a96d  mov     edi, r10d
0x18003a970  cmp     edi, edx
0x18003a972  jge     loc_18003AC49
0x18003a978  movsxd  r12, edi
0x18003a97b  lea     rbx, [r8+r12*8]
0x18003a97f  mov     rcx, [rbx]
0x18003a982  mov     rax, [rcx]
0x18003a985  mov     rax, [rax+258h]
0x18003a98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a991  test    eax, eax
0x18003a993  jnz     loc_18003AB48
0x18003a999  mov     rax, [rbp+4Fh+arg_20]
0x18003a99d  cmp     dword ptr [rax+r12*4], 0
0x18003a9a2  jnz     loc_18003ACAC
0x18003a9a8  test    rsi, rsi
0x18003a9ab  jz      loc_18003AC9E
0x18003a9b1  lea     rax, [rsi+9]
0x18003a9b5  cmp     rax, rsi
0x18003a9b8  jbe     loc_18003AE1E
0x18003a9be  mov     [rbp+4Fh+var_A0], rax
0x18003a9c2  cmp     r15d, 21h ; '!'
0x18003a9c6  jb      loc_18003ADB7
0x18003a9cc  lea     eax, [r15-9]
0x18003a9d0  mov     [rbp+4Fh+var_98], eax
0x18003a9d3  xor     eax, eax
0x18003a9d5  mov     [rbp+4Fh+var_B0], rsi
0x18003a9d9  mov     [rbp+4Fh+var_A8], r15d
0x18003a9dd  mov     r13, [rbx]
0x18003a9e0  mov     [rbp+4Fh+pExceptionObject], eax
0x18003a9e3  mov     rax, [rbp+4Fh+var_B8]
0x18003a9e7  lea     rcx, [rbp+4Fh+pExceptionObject]
0x18003a9eb  mov     [rsp+0F0h+var_D0], rcx
0x18003a9f0  xor     r9d, r9d
0x18003a9f3  xor     r8d, r8d
0x18003a9f6  mov     rdx, r13
0x18003a9f9  lea     rcx, [rbp+4Fh+var_B8]
0x18003a9fd  mov     rax, [rax+8]
0x18003aa01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa06  mov     ebx, eax
0x18003aa08  test    eax, eax
0x18003aa0a  jns     loc_18003AB08
0x18003aa10  cmp     eax, 8004103Ch
0x18003aa15  jnz     loc_18003AD8B
0x18003aa1b  mov     ebx, [rbp+4Fh+pExceptionObject]
0x18003aa1e  add     ebx, 18h
0x18003aa21  mov     rax, [rbp+4Fh+var_B8]
0x18003aa25  lea     rcx, [rbp+4Fh+var_B8]
0x18003aa29  mov     rax, [rax]
0x18003aa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa31  movzx   r9d, al
0x18003aa35  mov     r8, [rbp+4Fh+var_B0]
0x18003aa39  test    r8, r8
0x18003aa3c  jz      loc_18003AD07
0x18003aa42  mov     edx, ebx
0x18003aa44  add     rdx, 9
0x18003aa48  mov     ecx, [rbp+4Fh+var_A8]
0x18003aa4b  cmp     rcx, rdx
0x18003aa4e  jb      loc_18003AD84
0x18003aa54  xor     eax, eax
0x18003aa56  mov     [r8], rax
0x18003aa59  mov     [r8+8], al
0x18003aa5d  mov     rax, [rbp+4Fh+var_B0]
0x18003aa61  mov     dword ptr [rax], 9
0x18003aa67  mov     rax, [rbp+4Fh+var_B0]
0x18003aa6b  mov     [rax+4], ebx
0x18003aa6e  mov     rax, [rbp+4Fh+var_B0]
0x18003aa72  mov     [rax+8], r9b
0x18003aa76  xor     ebx, ebx
0x18003aa78  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa7f  lea     rax, WPP_GLOBAL_Control
0x18003aa86  cmp     rcx, rax
0x18003aa89  jz      short loc_18003AA95
0x18003aa8b  test    byte ptr [rcx+1Ch], 1
0x18003aa8f  jnz     loc_18003AD22
0x18003aa95  test    ebx, ebx
0x18003aa97  js      loc_18003AD8B
0x18003aa9d  mov     r8, [rbp+4Fh+var_A0]
0x18003aaa1  mov     dword ptr [r8], 18h
0x18003aaa8  mov     ecx, [rbp+4Fh+pExceptionObject]
0x18003aaab  mov     rax, [rbp+4Fh+var_A0]
0x18003aaaf  mov     [rax+4], ecx
0x18003aab2  add     r12, r12
0x18003aab5  mov     rax, [rbp+4Fh+var_A0]
0x18003aab9  mov     rcx, [rbp+4Fh+arg_18]
0x18003aabd  movups  xmm0, xmmword ptr [rcx+r12*8]
0x18003aac2  movups  xmmword ptr [rax+8], xmm0
0x18003aac6  mov     [rbp+4Fh+var_BC], 0
0x18003aacd  add     r8, 18h
0x18003aad1  mov     rax, [rbp+4Fh+var_B8]
0x18003aad5  lea     rcx, [rbp+4Fh+var_BC]
0x18003aad9  mov     [rsp+0F0h+var_D0], rcx
0x18003aade  mov     r9d, [rbp+4Fh+pExceptionObject]
0x18003aae2  mov     rdx, r13
0x18003aae5  lea     rcx, [rbp+4Fh+var_B8]
0x18003aae9  mov     rax, [rax+8]
0x18003aaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaf2  mov     ebx, eax
0x18003aaf4  test    eax, eax
0x18003aaf6  js      loc_18003AD8B
0x18003aafc  mov     r14d, [rbp+4Fh+pExceptionObject]
0x18003ab00  add     r14d, 21h ; '!'
0x18003ab04  mov     [rbp+4Fh+var_C0], r14d
0x18003ab08  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab0f  lea     rax, WPP_GLOBAL_Control
0x18003ab16  cmp     rcx, rax
0x18003ab19  jz      short loc_18003AB25
0x18003ab1b  test    byte ptr [rcx+1Ch], 1
0x18003ab1f  jnz     loc_18003AD49
0x18003ab25  mov     r13, [rbp+4Fh+arg_18]
0x18003ab29  test    ebx, ebx
0x18003ab2b  js      loc_18003AC49
0x18003ab31  inc     edi
0x18003ab33  mov     eax, r14d
0x18003ab36  add     rsi, rax
0x18003ab39  sub     r15d, r14d
0x18003ab3c  mov     edx, [rbp+4Fh+arg_8]
0x18003ab3f  mov     r8, [rbp+4Fh+arg_10]
0x18003ab43  jmp     loc_18003A970
0x18003ab48  test    rsi, rsi
0x18003ab4b  jnz     loc_18003ACDE
0x18003ab51  xor     eax, eax
0x18003ab53  mov     r12d, eax
0x18003ab56  mov     [rbp+4Fh+var_78], rax
0x18003ab5a  mov     [rbp+4Fh+var_70], eax
0x18003ab5d  mov     [rbp+4Fh+var_88], rsi
0x18003ab61  mov     [rbp+4Fh+var_80], r15d
0x18003ab65  mov     r13, [rbx]
0x18003ab68  mov     [rbp+4Fh+pExceptionObject], eax
0x18003ab6b  mov     rax, [r13+0]
0x18003ab6f  lea     r9, [rbp+4Fh+pExceptionObject]
0x18003ab73  xor     r8d, r8d
0x18003ab76  xor     edx, edx
0x18003ab78  mov     rcx, r13
0x18003ab7b  mov     rax, [rax+228h]
0x18003ab82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab87  mov     ebx, eax
0x18003ab89  test    eax, eax
0x18003ab8b  jns     short loc_18003AC01
0x18003ab8d  cmp     eax, 8004103Ch
0x18003ab92  jnz     loc_18003ADA1
0x18003ab98  mov     edx, [rbp+4Fh+pExceptionObject]
0x18003ab9b  add     edx, 8; unsigned int
0x18003ab9e  mov     r8b, 1; unsigned __int8
0x18003aba1  lea     rcx, [rbp+4Fh+var_88]; this
0x18003aba5  call    ?SetupObjectPacketHeader@CWbemObjectPacket@@IEAAJKE@Z; CWbemObjectPacket::SetupObjectPacketHeader(ulong,uchar)
0x18003abaa  mov     ebx, eax
0x18003abac  test    eax, eax
0x18003abae  js      loc_18003ADA1
0x18003abb4  mov     dword ptr [r12], 8
0x18003abbc  mov     eax, [rbp+4Fh+pExceptionObject]
0x18003abbf  mov     [r12+4], eax
0x18003abc4  mov     [rbp+4Fh+var_BC], 0
0x18003abcb  mov     rax, [r13+0]
0x18003abcf  lea     rdx, [r12+8]
0x18003abd4  lea     r9, [rbp+4Fh+var_BC]
0x18003abd8  mov     r8d, [rbp+4Fh+pExceptionObject]
0x18003abdc  mov     rcx, r13
0x18003abdf  mov     rax, [rax+228h]
0x18003abe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abeb  mov     ebx, eax
0x18003abed  test    eax, eax
0x18003abef  js      loc_18003ADA1
0x18003abf5  mov     r14d, [rbp+4Fh+pExceptionObject]
0x18003abf9  add     r14d, 11h
0x18003abfd  mov     [rbp+4Fh+var_C0], r14d
0x18003ac01  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac08  lea     rax, WPP_GLOBAL_Control
0x18003ac0f  cmp     rcx, rax
0x18003ac12  jz      loc_18003AB25
0x18003ac18  test    byte ptr [rcx+1Ch], 1
0x18003ac1c  jz      loc_18003AB25
0x18003ac22  cmp     byte ptr [rcx+19h], 2
0x18003ac26  jb      loc_18003AB25
0x18003ac2c  mov     edx, 10h
0x18003ac31  mov     r9d, ebx
0x18003ac34  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18003ac3b  mov     rcx, [rcx+10h]
0x18003ac3f  call    WPP_SF_d
0x18003ac44  jmp     loc_18003AB25
0x18003ac49  lea     rax, ??_7CWbemClasslessInstancePacket@@6B@; const CWbemClasslessInstancePacket::`vftable'
0x18003ac50  mov     [rbp+4Fh+var_B8], rax
0x18003ac54  lea     rax, ??_7CWbemInstancePacket@@6B@; const CWbemInstancePacket::`vftable'
0x18003ac5b  mov     [rbp+4Fh+var_B8], rax
0x18003ac5f  mov     [rbp+4Fh+var_68], rax
0x18003ac63  lea     r12, WPP_GLOBAL_Control
0x18003ac6a  test    ebx, ebx
0x18003ac6c  js      loc_18003AF58
0x18003ac72  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac79  cmp     rcx, r12
0x18003ac7c  jz      short loc_18003AC88
0x18003ac7e  test    byte ptr [rcx+1Ch], 1
0x18003ac82  jnz     loc_18003AD5D
0x18003ac88  mov     eax, ebx
0x18003ac8a  add     rsp, 0B8h
0x18003ac91  pop     r15
0x18003ac93  pop     r14
0x18003ac95  pop     r13
0x18003ac97  pop     r12
0x18003ac99  pop     rdi
0x18003ac9a  pop     rsi
0x18003ac9b  pop     rbx
0x18003ac9c  pop     rbp
0x18003ac9d  retn
0x18003ac9e  xor     eax, eax
0x18003aca0  mov     [rbp+4Fh+var_A0], rax
0x18003aca4  mov     [rbp+4Fh+var_98], eax
0x18003aca7  jmp     loc_18003A9D5
0x18003acac  shl     r12, 4
0x18003acb0  add     r12, r13
0x18003acb3  lea     rax, [rbp+4Fh+var_C0]
0x18003acb7  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18003acbc  mov     [rsp+0F0h+var_D0], r12; struct _GUID *
0x18003acc1  mov     r9, [rbx]; struct IWbemClassObject *
0x18003acc4  mov     r8d, r15d; unsigned int
0x18003acc7  mov     rdx, rsi; unsigned __int8 *
0x18003acca  lea     rcx, [rbp+4Fh+var_68]; this
0x18003acce  call    ?WriteToPacket@CWbemInstancePacket@@QEAAJPEAEKPEAUIWbemClassObject@@AEAU_GUID@@PEAK@Z; CWbemInstancePacket::WriteToPacket(uchar *,ulong,IWbemClassObject *,_GUID &,ulong *)
0x18003acd3  mov     ebx, eax
0x18003acd5  mov     r14d, [rbp+4Fh+var_C0]
0x18003acd9  jmp     loc_18003AB29
0x18003acde  lea     r12, [rsi+9]
0x18003ace2  cmp     r12, rsi
0x18003ace5  jbe     loc_18003AEEC
0x18003aceb  mov     [rbp+4Fh+var_78], r12
0x18003acef  cmp     r15d, 11h
0x18003acf3  jb      loc_18003AE85
0x18003acf9  lea     eax, [r15-9]
0x18003acfd  mov     [rbp+4Fh+var_70], eax
0x18003ad00  xor     eax, eax
0x18003ad02  jmp     loc_18003AB5D
0x18003ad07  mov     ebx, 80041008h
0x18003ad0c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ad12  mov     edx, ebx
0x18003ad14  mov     rcx, rax
0x18003ad17  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ad1d  jmp     loc_18003AA78
0x18003ad22  cmp     byte ptr [rcx+19h], 2
0x18003ad26  jb      loc_18003AA95
0x18003ad2c  mov     edx, 0Ah
0x18003ad31  mov     r9d, ebx
0x18003ad34  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
  ... truncated ...
```
