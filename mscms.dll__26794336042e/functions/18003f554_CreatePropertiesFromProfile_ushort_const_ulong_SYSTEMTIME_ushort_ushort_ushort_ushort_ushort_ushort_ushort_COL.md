# CreatePropertiesFromProfile(ushort const *,ulong *,_SYSTEMTIME *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,COLORPROFILETYPE *,COLORPROFILESUBTYPE *,ulong *,ushort * *,ushort * *,ushort * *,DmpDeviceType *)

- ea: `0x18003f554`
- end: `0x18003ff28`
- name: `?CreatePropertiesFromProfile@@YAJPEBGPEAKPEAU_SYSTEMTIME@@PEAPEAG333333PEAW4COLORPROFILETYPE@@PEAW4COLORPROFILESUBTYPE@@1333PEAW4DmpDeviceType@@@Z`
- size: `2516`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, struct _SYSTEMTIME *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, enum COLORPROFILETYPE *, enum COLORPROFILESUBTYPE *, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, enum DmpDeviceType *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180023a78`
- `0x18002435c`

## callees

- `0x180002658`
- `0x1800098b0`
- `0x180009e34`
- `0x18000b828`
- `0x18000be44`
- `0x180023a4c`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18003d8c8`
- `0x18003f554`
- `0x180046120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ff00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ff00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd45`

## pseudocode

```c
__int64 __fastcall CreatePropertiesFromProfile(
        unsigned __int16 *a1,
        unsigned int *a2,
        struct _SYSTEMTIME *a3,
        LPVOID *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10,
        enum COLORPROFILETYPE *a11,
        enum COLORPROFILESUBTYPE *a12,
        unsigned int *a13,
        unsigned __int16 **a14,
        unsigned __int16 **a15,
        unsigned __int16 **a16,
        enum DmpDeviceType *a17)
{
  int ProfileProperties; // ebx
  unsigned __int16 *v19; // r11
  __int16 v20; // dx
  unsigned __int64 v21; // rbx
  unsigned __int16 *v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int16 *v24; // rax
  unsigned __int64 v25; // rbx
  unsigned __int16 *v26; // rax
  unsigned __int64 v27; // rbx
  unsigned __int16 *v28; // rax
  unsigned __int64 v29; // rbx
  unsigned __int16 *v30; // rax
  unsigned __int64 v31; // rbx
  unsigned __int16 *v32; // rax
  unsigned __int64 v33; // rbx
  unsigned __int16 *v34; // rax
  unsigned __int64 v35; // rbx
  unsigned __int16 *v36; // rax
  unsigned __int64 v37; // rbx
  unsigned __int16 *v38; // rax
  unsigned __int64 v39; // rbx
  unsigned __int16 *v40; // rax
  const OLECHAR *v41; // r11
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  LPVOID *v45; // r15
  LPVOID *v46; // r15
  LPVOID *v47; // r15
  LPVOID *v48; // r15
  unsigned __int16 *v50; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v51; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v52; // [rsp+50h] [rbp-B0h]
  struct _SYSTEMTIME *v53; // [rsp+58h] [rbp-A8h]
  LPVOID *v54; // [rsp+60h] [rbp-A0h]
  LPVOID *v55; // [rsp+68h] [rbp-98h]
  LPVOID *v56; // [rsp+70h] [rbp-90h]
  enum COLORPROFILETYPE *v57; // [rsp+78h] [rbp-88h]
  enum COLORPROFILESUBTYPE *v58; // [rsp+80h] [rbp-80h]
  unsigned int *v59; // [rsp+88h] [rbp-78h]
  DWORD dwErrCode; // [rsp+90h] [rbp-70h]
  LPVOID *v61; // [rsp+98h] [rbp-68h]
  enum DmpDeviceType *v62; // [rsp+A0h] [rbp-60h]
  __int64 v63; // [rsp+A8h] [rbp-58h] BYREF
  const OLECHAR *v64; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v65[2]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v66[3]; // [rsp+C8h] [rbp-38h] BYREF
  struct _SYSTEMTIME v67; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 *v68; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v69; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v70; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v71; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v72; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v73; // [rsp+110h] [rbp+10h]
  unsigned __int16 v74[16]; // [rsp+118h] [rbp+18h] BYREF
  enum COLORPROFILETYPE v75; // [rsp+138h] [rbp+38h]
  enum COLORPROFILESUBTYPE v76; // [rsp+13Ch] [rbp+3Ch]
  unsigned int v77; // [rsp+140h] [rbp+40h]
  int v78; // [rsp+144h] [rbp+44h]
  unsigned __int16 v79[5]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 v80[5]; // [rsp+152h] [rbp+52h] BYREF
  unsigned __int16 v81[10]; // [rsp+15Ch] [rbp+5Ch] BYREF

  v54 = (LPVOID *)a8;
  v55 = (LPVOID *)a9;
  v56 = (LPVOID *)a10;
  v57 = a11;
  v58 = a12;
  v59 = a13;
  v62 = a17;
  v53 = a3;
  v52 = a2;
  v50 = a1;
  v61 = (LPVOID *)a7;
  dwErrCode = GetLastError();
  memset_0(v66, 0, 0xA0u);
  v65[0] = 1;
  v65[1] = (v53 != 0 ? 2 : 0)
         | (v52 != 0)
         | (a4 != 0 ? 4 : 0)
         | (a5 != 0 ? 8 : 0)
         | (a6 != 0 ? 0x10 : 0)
         | (a7 != 0 ? 0x20 : 0)
         | (a16 != 0 ? 0x4000 : 0)
         | (a8 != 0 ? 0x40 : 0)
         | (a9 != 0 ? 0x80 : 0)
         | (a10 != 0 ? 0x100 : 0)
         | (a11 != 0 ? 0x200 : 0)
         | (a17 != 0 ? 0x8000 : 0)
         | (a12 != 0 ? 0x400 : 0)
         | (a13 != 0 ? 0x800 : 0)
         | (a14 != 0 ? 0x1000 : 0)
         | (a15 != 0 ? 0x2000 : 0);
  if ( v52 )
    *v52 = 0;
  if ( v53 )
    *v53 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( v57 )
    *v57 = CPT_ICC;
  if ( v58 )
    *v58 = CPST_PERCEPTUAL;
  if ( v59 )
    *v59 = 0;
  if ( a14 )
    *a14 = 0;
  if ( a15 )
    *a15 = 0;
  if ( a16 )
    *a16 = 0;
  if ( a17 )
    *(_DWORD *)a17 = 0;
  v51 = 0;
  ProfileProperties = StringCchLengthW(v50, 0x104u, &v51);
  if ( ProfileProperties < 0 )
    goto LABEL_123;
  if ( !v51 )
  {
    ProfileProperties = -2147024809;
    goto LABEL_123;
  }
  ProfileProperties = InternalColorCplGetProfileProperties(v19, 1, (__int64)v65);
  if ( ProfileProperties < 0 )
    goto LABEL_123;
  v20 = v66[0];
  if ( v52 && (v66[0] & 1) != 0 )
    *v52 = v66[2];
  if ( v53 && (v20 & 2) != 0 )
    *v53 = v67;
  if ( a4 && (v20 & 4) != 0 && v68 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v68, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v21 = v51 + 1;
    v22 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *a4 = v22;
    if ( !v22 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v22, v21, v68);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( a5 && (v20 & 8) != 0 && v69 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v69, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v23 = v51 + 1;
    v24 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *a5 = v24;
    if ( !v24 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v24, v23, v69);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( a6 && (v20 & 0x10) != 0 && v70 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v70, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v25 = v51 + 1;
    v26 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *a6 = v26;
    if ( !v26 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v26, v25, v70);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( v61 && (v20 & 0x20) != 0 && v71 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v71, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v27 = v51 + 1;
    v28 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *v61 = v28;
    if ( !v28 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v28, v27, v71);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( v54 && (v20 & 0x40) != 0 && v73 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v73, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v29 = v51 + 1;
    v30 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *v54 = v30;
    if ( !v30 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v30, v29, v73);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( v55 && (v20 & 0x80u) != 0 && v72 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v72, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v31 = v51 + 1;
    v32 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *v55 = v32;
    if ( !v32 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v32, v31, v72);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( v56 && (v20 & 0x100) != 0 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v74, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v33 = v51 + 1;
    v34 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *v56 = v34;
    if ( !v34 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v34, v33, v74);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( v57 && (v20 & 0x200) != 0 )
    *v57 = v75;
  if ( v58 && (v20 & 0x400) != 0 )
    *v58 = v76;
  if ( v59 && (v20 & 0x800) != 0 )
    *v59 = v77;
  if ( a14 && (v20 & 0x1000) != 0 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v79, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v35 = v51 + 1;
    v36 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *a14 = v36;
    if ( !v36 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v36, v35, v79);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( a15 && (v20 & 0x2000) != 0 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v80, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v37 = v51 + 1;
    v38 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *a15 = v38;
    if ( !v38 )
      goto LABEL_48;
    ProfileProperties = StringCchCopyW(v38, v37, v80);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v20 = v66[0];
  }
  if ( a16 && (v20 & 0x4000) != 0 )
  {
    v51 = 0;
    ProfileProperties = StringCchLengthW(v81, 0x1F4u, &v51);
    if ( ProfileProperties < 0 )
      goto LABEL_123;
    v39 = v51 + 1;
    v40 = (unsigned __int16 *)MemAlloc(2 * (v51 + 1));
    *a16 = v40;
    if ( v40 )
    {
      ProfileProperties = StringCchCopyW(v40, v39, v81);
      if ( ProfileProperties >= 0 )
      {
        v20 = v66[0];
        goto LABEL_119;
      }
LABEL_123:
      if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
      {
        v63 = 0x2000000;
        v64 = v41;
        LODWORD(v50) = ProfileProperties;
        LODWORD(v51) = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v42,
          (__int64)&byte_180090E37,
          v43,
          v44,
          (__int64)&v50,
          (__int64)&v51,
          &v64,
          (__int64)&v63);
      }
      if ( v52 )
        *v52 = 0;
      if ( v53 )
        *v53 = 0;
      if ( a4 && *a4 )
      {
        MemFree(*a4);
        *a4 = 0;
      }
      if ( a5 && *a5 )
      {
        MemFree(*a5);
        *a5 = 0;
      }
      if ( a6 && *a6 )
      {
        MemFree(*a6);
        *a6 = 0;
      }
      v45 = v61;
      if ( v61 && *v61 )
      {
        MemFree(*v61);
        *v45 = 0;
      }
      v46 = v54;
      if ( v54 && *v54 )
      {
        MemFree(*v54);
        *v46 = 0;
      }
      v47 = v55;
      if ( v55 && *v55 )
      {
        MemFree(*v55);
        *v47 = 0;
      }
      v48 = v56;
      if ( v56 && *v56 )
      {
        MemFree(*v56);
        *v48 = 0;
      }
      if ( v57 )
        *v57 = CPT_ICC;
      if ( v58 )
        *v58 = CPST_PERCEPTUAL;
      if ( v59 )
        *v59 = 0;
      if ( a14 && *a14 )
      {
        MemFree(*a14);
        *a14 = 0;
      }
      if ( a15 && *a15 )
      {
        MemFree(*a15);
        *a15 = 0;
      }
      if ( a16 && *a16 )
      {
        MemFree(*a16);
        *a16 = 0;
      }
      if ( v62 )
        *(_DWORD *)v62 = 0;
      goto LABEL_168;
    }
LABEL_48:
    ProfileProperties = -2147024882;
    goto LABEL_123;
  }
LABEL_119:
  if ( v62 && v20 < 0 )
    *(_DWORD *)v62 = v78;
LABEL_168:
  InternalColorCplReleaseProfileProperties((struct COLOR_PROFILE_PROPERTIES *)v65);
  SetLastError(dwErrCode);
  return (unsigned int)ProfileProperties;
}

```

## disassembly

```asm
0x18003f554  push    rbp
0x18003f556  push    rbx
0x18003f557  push    rsi
0x18003f558  push    rdi
0x18003f559  push    r12
0x18003f55b  push    r13
0x18003f55d  push    r14
0x18003f55f  push    r15
0x18003f561  lea     rbp, [rsp-88h]
0x18003f569  sub     rsp, 188h
0x18003f570  mov     rax, cs:__security_cookie
0x18003f577  xor     rax, rsp
0x18003f57a  mov     [rbp+0C0h+var_50], rax
0x18003f57e  mov     rax, [rbp+0C0h+arg_38]
0x18003f585  mov     r15, r9
0x18003f588  mov     rbx, [rbp+0C0h+arg_30]
0x18003f58f  mov     r12, [rbp+0C0h+arg_20]
0x18003f596  mov     r13, [rbp+0C0h+arg_28]
0x18003f59d  mov     r14, [rbp+0C0h+arg_68]
0x18003f5a4  mov     rsi, [rbp+0C0h+arg_70]
0x18003f5ab  mov     rdi, [rbp+0C0h+arg_78]
0x18003f5b2  mov     [rsp+1C0h+var_160], rax
0x18003f5b7  mov     rax, [rbp+0C0h+arg_40]
0x18003f5be  mov     [rsp+1C0h+var_158], rax
0x18003f5c3  mov     rax, [rbp+0C0h+arg_48]
0x18003f5ca  mov     [rsp+1C0h+var_150], rax
0x18003f5cf  mov     rax, [rbp+0C0h+arg_50]
0x18003f5d6  mov     [rsp+1C0h+var_148], rax
0x18003f5db  mov     rax, [rbp+0C0h+arg_58]
0x18003f5e2  mov     [rbp+0C0h+var_140], rax
0x18003f5e6  mov     rax, [rbp+0C0h+arg_60]
0x18003f5ed  mov     [rbp+0C0h+var_138], rax
0x18003f5f1  mov     rax, [rbp+0C0h+arg_80]
0x18003f5f8  mov     [rbp+0C0h+var_120], rax
0x18003f5fc  mov     [rsp+1C0h+var_168], r8
0x18003f601  mov     [rsp+1C0h+var_170], rdx
0x18003f606  mov     [rsp+1C0h+var_180], rcx
0x18003f60b  mov     [rbp+0C0h+var_128], rbx
0x18003f60f  call    cs:__imp_GetLastError
0x18003f615  xor     edx, edx; Val
0x18003f617  lea     rcx, [rbp+0C0h+var_F8]; void *
0x18003f61b  mov     r8d, 0A0h; Size
0x18003f621  mov     [rbp+0C0h+dwErrCode], eax
0x18003f624  call    memset_0
0x18003f629  mov     rax, [rbp+0C0h+var_138]
0x18003f62d  mov     rcx, rsi
0x18003f630  mov     r11, [rbp+0C0h+var_120]
0x18003f634  neg     rcx
0x18003f637  mov     r10, [rsp+1C0h+var_150]
0x18003f63c  mov     rcx, r14
0x18003f63f  sbb     r8d, r8d
0x18003f642  mov     r9, [rsp+1C0h+var_158]
0x18003f647  and     r8d, 2000h
0x18003f64e  mov     [rbp+0C0h+var_100], 1
0x18003f655  neg     rcx
0x18003f658  sbb     edx, edx
0x18003f65a  and     edx, 1000h
0x18003f660  or      r8d, edx
0x18003f663  mov     rdx, [rsp+1C0h+var_160]
0x18003f668  neg     rax
0x18003f66b  mov     rax, [rbp+0C0h+var_140]
0x18003f66f  sbb     ecx, ecx
0x18003f671  and     ecx, 800h
0x18003f677  or      r8d, ecx
0x18003f67a  neg     rax
0x18003f67d  mov     rax, r11
0x18003f680  sbb     ecx, ecx
0x18003f682  and     ecx, 400h
0x18003f688  or      r8d, ecx
0x18003f68b  neg     rax
0x18003f68e  mov     rax, [rsp+1C0h+var_148]
0x18003f693  sbb     ecx, ecx
0x18003f695  and     ecx, 8000h
0x18003f69b  or      r8d, ecx
0x18003f69e  neg     rax
0x18003f6a1  mov     rax, r10
0x18003f6a4  sbb     ecx, ecx
0x18003f6a6  and     ecx, 200h
0x18003f6ac  or      r8d, ecx
0x18003f6af  neg     rax
0x18003f6b2  mov     rax, r9
0x18003f6b5  sbb     ecx, ecx
0x18003f6b7  and     ecx, 100h
0x18003f6bd  or      r8d, ecx
0x18003f6c0  neg     rax
0x18003f6c3  mov     rax, rdx
0x18003f6c6  sbb     ecx, ecx
0x18003f6c8  and     ecx, 80h
0x18003f6ce  or      r8d, ecx
0x18003f6d1  neg     rax
0x18003f6d4  mov     rax, rdi
0x18003f6d7  sbb     ecx, ecx
0x18003f6d9  and     ecx, 40h
0x18003f6dc  or      r8d, ecx
0x18003f6df  neg     rax
0x18003f6e2  mov     rax, rbx
0x18003f6e5  sbb     ecx, ecx
0x18003f6e7  and     ecx, 4000h
0x18003f6ed  or      r8d, ecx
0x18003f6f0  neg     rax
0x18003f6f3  mov     rax, r13
0x18003f6f6  sbb     ecx, ecx
0x18003f6f8  and     ecx, 20h
0x18003f6fb  or      r8d, ecx
0x18003f6fe  neg     rax
0x18003f701  mov     rax, r12
0x18003f704  sbb     ecx, ecx
0x18003f706  and     ecx, 10h
0x18003f709  or      r8d, ecx
0x18003f70c  neg     rax
0x18003f70f  mov     rax, r15
0x18003f712  sbb     ecx, ecx
0x18003f714  and     ecx, 8
0x18003f717  or      r8d, ecx
0x18003f71a  neg     rax
0x18003f71d  sbb     ecx, ecx
0x18003f71f  xor     eax, eax
0x18003f721  and     ecx, 4
0x18003f724  or      r8d, ecx
0x18003f727  cmp     [rsp+1C0h+var_170], rax
0x18003f72c  setnz   al
0x18003f72f  or      r8d, eax
0x18003f732  mov     rax, [rsp+1C0h+var_168]
0x18003f737  neg     rax
0x18003f73a  mov     rax, [rsp+1C0h+var_170]
0x18003f73f  sbb     ecx, ecx
0x18003f741  and     ecx, 2
0x18003f744  or      r8d, ecx
0x18003f747  xor     ecx, ecx
0x18003f749  mov     [rbp+0C0h+var_FC], r8d
0x18003f74d  test    rax, rax
0x18003f750  jz      short loc_18003F754
0x18003f752  mov     [rax], ecx
0x18003f754  mov     rax, [rsp+1C0h+var_168]
0x18003f759  test    rax, rax
0x18003f75c  jz      short loc_18003F765
0x18003f75e  xorps   xmm0, xmm0
0x18003f761  movdqu  xmmword ptr [rax], xmm0
0x18003f765  test    r15, r15
0x18003f768  jz      short loc_18003F76D
0x18003f76a  mov     [r15], rcx
0x18003f76d  test    r12, r12
0x18003f770  jz      short loc_18003F776
0x18003f772  mov     [r12], rcx
0x18003f776  test    r13, r13
0x18003f779  jz      short loc_18003F77F
0x18003f77b  mov     [r13+0], rcx
0x18003f77f  test    rbx, rbx
0x18003f782  jz      short loc_18003F787
0x18003f784  mov     [rbx], rcx
0x18003f787  test    rdx, rdx
0x18003f78a  jz      short loc_18003F78F
0x18003f78c  mov     [rdx], rcx
0x18003f78f  test    r9, r9
0x18003f792  jz      short loc_18003F797
0x18003f794  mov     [r9], rcx
0x18003f797  test    r10, r10
0x18003f79a  jz      short loc_18003F79F
0x18003f79c  mov     [r10], rcx
0x18003f79f  mov     rax, [rsp+1C0h+var_148]
0x18003f7a4  test    rax, rax
0x18003f7a7  jz      short loc_18003F7AB
0x18003f7a9  mov     [rax], ecx
0x18003f7ab  mov     rax, [rbp+0C0h+var_140]
0x18003f7af  test    rax, rax
0x18003f7b2  jz      short loc_18003F7B6
0x18003f7b4  mov     [rax], ecx
0x18003f7b6  mov     rax, [rbp+0C0h+var_138]
0x18003f7ba  test    rax, rax
0x18003f7bd  jz      short loc_18003F7C1
0x18003f7bf  mov     [rax], ecx
0x18003f7c1  test    r14, r14
0x18003f7c4  jz      short loc_18003F7C9
0x18003f7c6  mov     [r14], rcx
0x18003f7c9  test    rsi, rsi
0x18003f7cc  jz      short loc_18003F7D1
0x18003f7ce  mov     [rsi], rcx
0x18003f7d1  test    rdi, rdi
0x18003f7d4  jz      short loc_18003F7D9
0x18003f7d6  mov     [rdi], rcx
0x18003f7d9  test    r11, r11
0x18003f7dc  jz      short loc_18003F7E1
0x18003f7de  mov     [r11], ecx
0x18003f7e1  mov     r11, [rsp+1C0h+var_180]
0x18003f7e6  lea     r8, [rsp+1C0h+var_178]; unsigned __int64 *
0x18003f7eb  mov     [rsp+1C0h+var_178], rcx
0x18003f7f0  mov     edx, 104h; unsigned __int64
0x18003f7f5  mov     rcx, r11; unsigned __int16 *
0x18003f7f8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003f7fd  mov     ebx, eax
0x18003f7ff  test    eax, eax
0x18003f801  js      loc_18003FD14
0x18003f807  cmp     [rsp+1C0h+var_178], 0
0x18003f80d  ja      short loc_18003F819
0x18003f80f  mov     ebx, 80070057h
0x18003f814  jmp     loc_18003FD14
0x18003f819  lea     r8, [rbp+0C0h+var_100]
0x18003f81d  mov     dl, 1
0x18003f81f  mov     rcx, r11; unsigned __int16 *
0x18003f822  call    InternalColorCplGetProfileProperties
0x18003f827  mov     ebx, eax
0x18003f829  test    eax, eax
0x18003f82b  js      loc_18003FD0F
0x18003f831  mov     rcx, [rsp+1C0h+var_170]
0x18003f836  mov     edx, [rbp+0C0h+var_F8]
0x18003f839  test    rcx, rcx
0x18003f83c  jz      short loc_18003F848
0x18003f83e  test    dl, 1
0x18003f841  jz      short loc_18003F848
0x18003f843  mov     eax, [rbp+0C0h+var_F0]
0x18003f846  mov     [rcx], eax
0x18003f848  mov     rcx, [rsp+1C0h+var_168]
0x18003f84d  test    rcx, rcx
0x18003f850  jz      short loc_18003F85F
0x18003f852  test    dl, 2
0x18003f855  jz      short loc_18003F85F
0x18003f857  movups  xmm0, [rbp+0C0h+var_EC]
0x18003f85b  movdqu  xmmword ptr [rcx], xmm0
0x18003f85f  test    r15, r15
0x18003f862  jz      short loc_18003F8D3
0x18003f864  test    dl, 4
0x18003f867  jz      short loc_18003F8D3
0x18003f869  mov     rcx, [rbp+0C0h+var_D8]; unsigned __int16 *
0x18003f86d  test    rcx, rcx
0x18003f870  jz      short loc_18003F8D3
0x18003f872  lea     r8, [rsp+1C0h+var_178]; unsigned __int64 *
0x18003f877  mov     [rsp+1C0h+var_178], 0
0x18003f880  mov     edx, 1F4h; unsigned __int64
0x18003f885  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003f88a  mov     ebx, eax
0x18003f88c  test    eax, eax
0x18003f88e  js      loc_18003FD0F
0x18003f894  mov     rbx, [rsp+1C0h+var_178]
0x18003f899  inc     rbx
0x18003f89c  lea     rcx, [rbx+rbx]
0x18003f8a0  call    MemAlloc
0x18003f8a5  mov     [r15], rax
0x18003f8a8  test    rax, rax
0x18003f8ab  jnz     short loc_18003F8B7
0x18003f8ad  mov     ebx, 8007000Eh
0x18003f8b2  jmp     loc_18003FD0F
0x18003f8b7  mov     r8, [rbp+0C0h+var_D8]; unsigned __int16 *
0x18003f8bb  mov     rdx, rbx; unsigned __int64
0x18003f8be  mov     rcx, rax; unsigned __int16 *
0x18003f8c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f8c6  mov     ebx, eax
0x18003f8c8  test    eax, eax
0x18003f8ca  js      loc_18003FD0F
0x18003f8d0  mov     edx, [rbp+0C0h+var_F8]
0x18003f8d3  test    r12, r12
0x18003f8d6  jz      short loc_18003F93E
0x18003f8d8  test    dl, 8
0x18003f8db  jz      short loc_18003F93E
0x18003f8dd  mov     rcx, [rbp+0C0h+var_D0]; unsigned __int16 *
0x18003f8e1  test    rcx, rcx
0x18003f8e4  jz      short loc_18003F93E
0x18003f8e6  lea     r8, [rsp+1C0h+var_178]; unsigned __int64 *
0x18003f8eb  mov     [rsp+1C0h+var_178], 0
0x18003f8f4  mov     edx, 1F4h; unsigned __int64
0x18003f8f9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003f8fe  mov     ebx, eax
0x18003f900  test    eax, eax
0x18003f902  js      loc_18003FD0F
0x18003f908  mov     rbx, [rsp+1C0h+var_178]
0x18003f90d  inc     rbx
0x18003f910  lea     rcx, [rbx+rbx]
0x18003f914  call    MemAlloc
0x18003f919  mov     [r12], rax
0x18003f91d  test    rax, rax
0x18003f920  jz      short loc_18003F8AD
0x18003f922  mov     r8, [rbp+0C0h+var_D0]; unsigned __int16 *
0x18003f926  mov     rdx, rbx; unsigned __int64
0x18003f929  mov     rcx, rax; unsigned __int16 *
0x18003f92c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f931  mov     ebx, eax
0x18003f933  test    eax, eax
0x18003f935  js      loc_18003FD0F
0x18003f93b  mov     edx, [rbp+0C0h+var_F8]
0x18003f93e  test    r13, r13
0x18003f941  jz      short loc_18003F9AD
0x18003f943  test    dl, 10h
0x18003f946  jz      short loc_18003F9AD
0x18003f948  mov     rcx, [rbp+0C0h+var_C8]; unsigned __int16 *
0x18003f94c  test    rcx, rcx
0x18003f94f  jz      short loc_18003F9AD
0x18003f951  lea     r8, [rsp+1C0h+var_178]; unsigned __int64 *
0x18003f956  mov     [rsp+1C0h+var_178], 0
0x18003f95f  mov     edx, 1F4h; unsigned __int64
0x18003f964  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003f969  mov     ebx, eax
0x18003f96b  test    eax, eax
0x18003f96d  js      loc_18003FD0F
0x18003f973  mov     rbx, [rsp+1C0h+var_178]
0x18003f978  inc     rbx
0x18003f97b  lea     rcx, [rbx+rbx]
0x18003f97f  call    MemAlloc
0x18003f984  mov     [r13+0], rax
0x18003f988  test    rax, rax
0x18003f98b  jz      loc_18003F8AD
0x18003f991  mov     r8, [rbp+0C0h+var_C8]; unsigned __int16 *
  ... truncated ...
```
