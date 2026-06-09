# CMSDiscRecorderObj::SetRecorderProperties(IPropertyStorage *)

- ea: `0x180010170`
- end: `0x18001070d`
- name: `?SetRecorderProperties@CMSDiscRecorderObj@@UEAAJPEAUIPropertyStorage@@@Z`
- size: `1437`
- prototype: `__int64 __fastcall(CMSDiscRecorderObj *__hidden this, struct IPropertyStorage *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180007bac`
- `0x180007d40`
- `0x180007d80`
- `0x180010170`
- `0x1800133d8`
- `0x180014c50`
- `0x1800184da`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180010636`
- `ole32!CoTaskMemFree` at `0x180010636`
- `ole32!PropVariantClear` at `0x18001043e`
- `ole32!PropVariantClear` at `0x180010624`
- `ole32!PropVariantClear` at `0x18001043e`
- `ole32!PropVariantClear` at `0x180010624`
- `KERNEL32!LeaveCriticalSection` at `0x1800106bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800106bd`
- `KERNEL32!EnterCriticalSection` at `0x1800101e5`
- `KERNEL32!EnterCriticalSection` at `0x1800101e5`

## string_xrefs

- `0x1800102b6`: `MaxWriteSpeed`
- `0x1800102e0`: `MaxWriteSpeed`
- `0x180010374`: `MaxWriteSpeed`
- `0x180010340`: `WriteSpeed`
- `0x18001035e`: `WriteSpeed`

## pseudocode

```c
__int64 __fastcall CMSDiscRecorderObj::SetRecorderProperties(CMSDiscRecorderObj *this, struct IPropertyStorage *a2)
{
  int Property; // edi
  char v5; // r14
  int v6; // eax
  wchar_t *v7; // rbx
  char v8; // bl
  char v9; // al
  PROPVARIANT *v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  char v13; // bl
  char v14; // al
  char v15; // cl
  int v16; // eax
  __int64 v18; // [rsp+30h] [rbp-49h] BYREF
  wchar_t *String1[2]; // [rsp+38h] [rbp-41h] BYREF
  int v20; // [rsp+48h] [rbp-31h] BYREF
  const wchar_t *v21; // [rsp+50h] [rbp-29h]
  int v22; // [rsp+58h] [rbp-21h] BYREF
  const wchar_t *v23; // [rsp+60h] [rbp-19h]
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1h]
  __int128 v26; // [rsp+80h] [rbp+7h] BYREF
  __int64 v27; // [rsp+90h] [rbp+17h]
  int v28; // [rsp+E0h] [rbp+67h] BYREF
  int v29; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v30; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids, (char *)this - 8);
  v30 = 0;
  v29 = 0;
  v28 = 0;
  *(_OWORD *)String1 = 0;
  v18 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  if ( !*((_BYTE *)this + 140) )
  {
    Property = -2147220980;
    goto LABEL_75;
  }
  if ( !a2 )
  {
    Property = -2147023116;
    goto LABEL_75;
  }
  if ( !*((_QWORD *)this + 16) )
  {
    Property = 262656;
    goto LABEL_75;
  }
  Property = ((__int64 (__fastcall *)(struct IPropertyStorage *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IPropertyStorage,
               &v18);
  if ( Property >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 16) + 88LL))(*((_QWORD *)this + 16), &v30) >= 0 )
    {
      v25 = 0;
      *(_OWORD *)pvar = 0;
      v27 = 0;
      v5 = 0;
      v26 = 0;
      while ( 1 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *))(*(_QWORD *)v30 + 24LL))(
               v30,
               1,
               String1,
               &v29);
        if ( v6 < 0 || v6 == 1 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v16 = Property;
          if ( v5 )
            v16 = 262656;
          Property = v16;
          goto LABEL_75;
        }
        v7 = String1[0];
        if ( !wcscmp_0(String1[0], L"MaxWriteSpeed") )
        {
          v20 = 0;
          v21 = L"MaxWriteSpeed";
          v8 = v5;
          if ( ((int (__fastcall *)(struct IPropertyStorage *, __int64, int *, PROPVARIANT *))a2->lpVtbl->ReadMultiple)(
                 a2,
                 1,
                 &v20,
                 pvar) < 0 )
            v8 = 1;
          Property = WriterGetProperty((char *)this + 72, 2, &v28);
          v9 = v8;
          if ( Property < 0 )
            v9 = 1;
          v5 = v9;
          if ( v28 != LODWORD(pvar[1]) )
            v5 = 1;
          goto LABEL_61;
        }
        if ( !wcscmp_0(v7, L"WriteSpeed") )
          break;
        if ( !wcscmp_0(v7, L"AudioGapSize") )
        {
          v20 = 0;
          v21 = L"AudioGapSize";
          Property = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, PROPVARIANT *))a2->lpVtbl->ReadMultiple)(
                       a2,
                       1,
                       &v20,
                       pvar);
          if ( Property < 0 )
            goto LABEL_75;
          if ( LOWORD(pvar[0]) != 3 || LODWORD(pvar[1]) > 0xE1 )
            goto LABEL_60;
          Property = WriterSetProperty((char *)this + 72, 3);
          if ( Property < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_75;
            v12 = 30;
LABEL_68:
            WPP_SF_(v11[7], v12, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids);
            goto LABEL_75;
          }
LABEL_58:
          Property = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(**((_QWORD **)this + 16)
                                                                                           + 32LL))(
                       *((_QWORD *)this + 16),
                       1,
                       &v20,
                       pvar,
                       2);
          if ( Property < 0 )
            goto LABEL_75;
          goto LABEL_61;
        }
        if ( !wcscmp_0(v7, L"BufferUnderrunFreeCapable") )
        {
          v20 = 0;
          v21 = L"BufferUnderrunFreeCapable";
          v13 = v5;
          if ( ((int (__fastcall *)(struct IPropertyStorage *, __int64, int *, PROPVARIANT *))a2->lpVtbl->ReadMultiple)(
                 a2,
                 1,
                 &v20,
                 pvar) < 0 )
            v13 = 1;
          Property = WriterGetProperty((char *)this + 72, 4, &v28);
          v14 = v13;
          if ( Property < 0 )
            v14 = 1;
          v15 = v14;
          if ( v28 != LODWORD(pvar[1]) )
            v15 = 1;
          v5 = v15;
          goto LABEL_61;
        }
        if ( !wcscmp_0(v7, L"EnableBufferUnderrunFree") )
        {
          v20 = 0;
          v21 = L"EnableBufferUnderrunFree";
          Property = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, PROPVARIANT *))a2->lpVtbl->ReadMultiple)(
                       a2,
                       1,
                       &v20,
                       pvar);
          if ( Property < 0 )
            goto LABEL_75;
          if ( LOWORD(pvar[0]) == 3 && (unsigned int)(LODWORD(pvar[1]) + 1) <= 2 )
          {
            Property = WriterSetProperty((char *)this + 72, 5);
            if ( Property < 0 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                v12 = 31;
                goto LABEL_68;
              }
              goto LABEL_75;
            }
            goto LABEL_58;
          }
LABEL_60:
          v5 = 1;
LABEL_61:
          v10 = pvar;
LABEL_62:
          PropVariantClear(v10);
          v7 = String1[0];
          goto LABEL_64;
        }
        v5 = 1;
LABEL_64:
        CoTaskMemFree(v7);
      }
      v20 = 0;
      v22 = 0;
      v21 = L"WriteSpeed";
      v23 = L"MaxWriteSpeed";
      Property = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, PROPVARIANT *))a2->lpVtbl->ReadMultiple)(
                   a2,
                   1,
                   &v20,
                   pvar);
      if ( Property < 0 )
        goto LABEL_75;
      Property = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, __int128 *))(**((_QWORD **)this + 16) + 24LL))(
                   *((_QWORD *)this + 16),
                   1,
                   &v22,
                   &v26);
      if ( Property < 0 )
        goto LABEL_75;
      if ( LOWORD(pvar[0]) == 3 && (_WORD)v26 == 3 && (SLODWORD(pvar[1]) <= SDWORD2(v26) || LODWORD(pvar[1]) == -1) )
      {
        Property = WriterSetProperty((char *)this + 72, 1);
        if ( Property < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_75;
          v12 = 29;
          goto LABEL_68;
        }
        if ( LODWORD(pvar[1]) == -1 )
          LODWORD(pvar[1]) = DWORD2(v26);
        Property = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(**((_QWORD **)this + 16)
                                                                                         + 32LL))(
                     *((_QWORD *)this + 16),
                     1,
                     &v20,
                     pvar,
                     2);
        if ( Property < 0 )
          goto LABEL_75;
      }
      else
      {
        v5 = 1;
      }
      PropVariantClear(pvar);
      v10 = (PROPVARIANT *)&v26;
      goto LABEL_62;
    }
  }
LABEL_75:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      32,
      WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids,
      (char *)this - 8,
      Property);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180010170  mov     [rsp-8+arg_8], rbx
0x180010175  push    rbp
0x180010176  push    rsi
0x180010177  push    rdi
0x180010178  push    r12
0x18001017a  push    r13
0x18001017c  push    r14
0x18001017e  push    r15
0x180010180  lea     rbp, [rsp-27h]
0x180010185  sub     rsp, 0A0h
0x18001018c  mov     r15, rdx
0x18001018f  mov     rsi, rcx
0x180010192  mov     rcx, cs:WPP_GLOBAL_Control
0x180010199  lea     rax, WPP_GLOBAL_Control
0x1800101a0  cmp     rcx, rax
0x1800101a3  jz      short loc_1800101C4
0x1800101a5  test    byte ptr [rcx+44h], 1
0x1800101a9  jz      short loc_1800101C4
0x1800101ab  mov     rcx, [rcx+38h]
0x1800101af  lea     r9, [rsi-8]
0x1800101b3  mov     edx, 1Ch
0x1800101b8  lea     r8, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x1800101bf  call    WPP_SF_q
0x1800101c4  xor     ebx, ebx
0x1800101c6  lea     r12, [rsi+0B8h]
0x1800101cd  xorps   xmm0, xmm0
0x1800101d0  mov     [rbp+57h+arg_18], rbx
0x1800101d4  mov     rcx, r12; lpCriticalSection
0x1800101d7  mov     [rbp+57h+arg_10], ebx
0x1800101da  mov     [rbp+57h+arg_0], ebx
0x1800101dd  movups  xmmword ptr [rbp+57h+String1], xmm0
0x1800101e1  mov     [rbp+57h+var_A0], rbx
0x1800101e5  call    cs:__imp_EnterCriticalSection
0x1800101eb  lea     r13, [rsi-8]
0x1800101ef  cmp     [r13+94h], bl
0x1800101f6  jnz     short loc_180010202
0x1800101f8  mov     edi, 8004020Ch
0x1800101fd  jmp     loc_1800106AE
0x180010202  test    r15, r15
0x180010205  jnz     short loc_180010211
0x180010207  mov     edi, 800706F4h
0x18001020c  jmp     loc_1800106AE
0x180010211  cmp     [rsi+80h], rbx
0x180010218  jnz     short loc_180010224
0x18001021a  mov     edi, 40200h
0x18001021f  jmp     loc_1800106AE
0x180010224  mov     rax, [r15]
0x180010227  lea     r8, [rbp+57h+var_A0]
0x18001022b  lea     rdx, IID_IPropertyStorage
0x180010232  mov     rcx, r15
0x180010235  mov     rax, [rax]
0x180010238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001023d  mov     edi, eax
0x18001023f  test    eax, eax
0x180010241  js      loc_1800106AE
0x180010247  mov     rcx, [rbp+57h+var_A0]
0x18001024b  mov     rdx, [rcx]
0x18001024e  mov     rax, [rdx+10h]
0x180010252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010257  mov     rcx, [rsi+80h]
0x18001025e  mov     rdx, [rcx]
0x180010261  mov     rax, [rdx+58h]
0x180010265  lea     rdx, [rbp+57h+arg_18]
0x180010269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001026e  test    eax, eax
0x180010270  js      loc_1800106AE
0x180010276  xor     eax, eax
0x180010278  xorps   xmm0, xmm0
0x18001027b  xorps   xmm1, xmm1
0x18001027e  mov     [rbp+57h+var_58], rax
0x180010282  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180010286  mov     [rbp+57h+var_40], rax
0x18001028a  mov     r14b, bl
0x18001028d  movups  [rbp+57h+var_50], xmm1
0x180010291  mov     rcx, [rbp+57h+arg_18]
0x180010295  lea     r9, [rbp+57h+arg_10]
0x180010299  lea     r8, [rbp+57h+String1]
0x18001029d  mov     edx, 1
0x1800102a2  mov     rax, [rcx]
0x1800102a5  mov     rax, [rax+18h]
0x1800102a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ae  test    eax, eax
0x1800102b0  js      loc_18001068F
0x1800102b6  lea     rcx, aMaxwritespeed; "MaxWriteSpeed"
0x1800102bd  cmp     eax, 1
0x1800102c0  jz      loc_18001068F
0x1800102c6  mov     rbx, [rbp+57h+String1]
0x1800102ca  mov     rdx, rcx; String2
0x1800102cd  mov     rcx, rbx; String1
0x1800102d0  call    wcscmp_0
0x1800102d5  test    eax, eax
0x1800102d7  jnz     short loc_180010340
0x1800102d9  mov     [rbp+57h+var_88], eax
0x1800102dc  lea     r9, [rbp+57h+pvar]
0x1800102e0  lea     rax, aMaxwritespeed; "MaxWriteSpeed"
0x1800102e7  mov     edi, 1
0x1800102ec  mov     [rbp+57h+var_80], rax
0x1800102f0  lea     r8, [rbp+57h+var_88]
0x1800102f4  mov     rax, [r15]
0x1800102f7  mov     edx, edi
0x1800102f9  mov     rcx, r15
0x1800102fc  mov     rax, [rax+18h]
0x180010300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010305  test    eax, eax
0x180010307  movzx   ebx, r14b
0x18001030b  lea     rcx, [rsi+48h]
0x18001030f  lea     r8, [rbp+57h+arg_0]
0x180010313  cmovs   ebx, edi
0x180010316  lea     edx, [rdi+1]
0x180010319  call    WriterGetProperty
0x18001031e  mov     edi, eax
0x180010320  mov     ecx, 1
0x180010325  test    edi, edi
0x180010327  movzx   eax, bl
0x18001032a  cmovs   eax, ecx
0x18001032d  movzx   r14d, al
0x180010331  mov     eax, dword ptr [rbp+57h+pvar+8]
0x180010334  cmp     [rbp+57h+arg_0], eax
0x180010337  cmovnz  r14d, ecx
0x18001033b  jmp     loc_180010620
0x180010340  lea     rdx, aWritespeed; "WriteSpeed"
0x180010347  mov     rcx, rbx; String1
0x18001034a  call    wcscmp_0
0x18001034f  test    eax, eax
0x180010351  jnz     loc_18001044D
0x180010357  mov     [rbp+57h+var_88], eax
0x18001035a  lea     r9, [rbp+57h+pvar]
0x18001035e  lea     rax, aWritespeed; "WriteSpeed"
0x180010365  mov     [rbp+57h+var_78], 0
0x18001036c  mov     [rbp+57h+var_80], rax
0x180010370  lea     r8, [rbp+57h+var_88]
0x180010374  lea     rax, aMaxwritespeed; "MaxWriteSpeed"
0x18001037b  mov     ebx, 1
0x180010380  mov     [rbp+57h+var_70], rax
0x180010384  mov     edx, ebx
0x180010386  mov     rax, [r15]
0x180010389  mov     rcx, r15
0x18001038c  mov     rax, [rax+18h]
0x180010390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010395  mov     edi, eax
0x180010397  test    eax, eax
0x180010399  js      loc_1800106B3
0x18001039f  mov     rcx, [rsi+80h]
0x1800103a6  lea     r9, [rbp+57h+var_50]
0x1800103aa  lea     r8, [rbp+57h+var_78]
0x1800103ae  mov     edx, ebx
0x1800103b0  mov     rax, [rcx]
0x1800103b3  mov     rax, [rax+18h]
0x1800103b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103bc  mov     edi, eax
0x1800103be  test    eax, eax
0x1800103c0  js      loc_1800106B3
0x1800103c6  lea     eax, [rbx+2]
0x1800103c9  cmp     word ptr [rbp+57h+pvar], ax
0x1800103cd  jnz     short loc_180010437
0x1800103cf  cmp     word ptr [rbp+57h+var_50], ax
0x1800103d3  jnz     short loc_180010437
0x1800103d5  mov     r8d, dword ptr [rbp+57h+pvar+8]
0x1800103d9  cmp     r8d, dword ptr [rbp+57h+var_50+8]
0x1800103dd  jle     short loc_1800103E5
0x1800103df  cmp     r8d, 0FFFFFFFFh
0x1800103e3  jnz     short loc_180010437
0x1800103e5  lea     rcx, [rsi+48h]
0x1800103e9  mov     edx, ebx
0x1800103eb  call    WriterSetProperty
0x1800103f0  mov     edi, eax
0x1800103f2  test    eax, eax
0x1800103f4  js      loc_180010641
0x1800103fa  cmp     dword ptr [rbp+57h+pvar+8], 0FFFFFFFFh
0x1800103fe  jnz     short loc_180010406
0x180010400  mov     eax, dword ptr [rbp+57h+var_50+8]
0x180010403  mov     dword ptr [rbp+57h+pvar+8], eax
0x180010406  mov     rcx, [rsi+80h]
0x18001040d  lea     r9, [rbp+57h+pvar]
0x180010411  lea     r8, [rbp+57h+var_88]
0x180010415  mov     [rsp+0D0h+var_B0], 2
0x18001041d  mov     edx, ebx
0x18001041f  mov     rax, [rcx]
0x180010422  mov     rax, [rax+20h]
0x180010426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001042b  mov     edi, eax
0x18001042d  test    eax, eax
0x18001042f  js      loc_1800106B3
0x180010435  jmp     short loc_18001043A
0x180010437  mov     r14b, bl
0x18001043a  lea     rcx, [rbp+57h+pvar]; pvar
0x18001043e  call    cs:__imp_PropVariantClear
0x180010444  lea     rcx, [rbp+57h+var_50]
0x180010448  jmp     loc_180010624
0x18001044d  lea     rdx, aAudiogapsize; "AudioGapSize"
0x180010454  mov     rcx, rbx; String1
0x180010457  call    wcscmp_0
0x18001045c  test    eax, eax
0x18001045e  jnz     loc_1800104F5
0x180010464  mov     [rbp+57h+var_88], eax
0x180010467  lea     r9, [rbp+57h+pvar]
0x18001046b  lea     rax, aAudiogapsize; "AudioGapSize"
0x180010472  mov     ebx, 1
0x180010477  mov     [rbp+57h+var_80], rax
0x18001047b  lea     r8, [rbp+57h+var_88]
0x18001047f  mov     rax, [r15]
0x180010482  mov     edx, ebx
0x180010484  mov     rcx, r15
0x180010487  mov     rax, [rax+18h]
0x18001048b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010490  mov     edi, eax
0x180010492  test    eax, eax
0x180010494  js      loc_1800106B3
0x18001049a  lea     eax, [rbx+2]
0x18001049d  cmp     word ptr [rbp+57h+pvar], ax
0x1800104a1  jnz     loc_18001061D
0x1800104a7  mov     r8d, dword ptr [rbp+57h+pvar+8]
0x1800104ab  cmp     r8d, 0E1h
0x1800104b2  ja      loc_18001061D
0x1800104b8  lea     rcx, [rsi+48h]
0x1800104bc  mov     edx, eax
0x1800104be  call    WriterSetProperty
0x1800104c3  mov     edi, eax
0x1800104c5  test    eax, eax
0x1800104c7  jns     loc_1800105EC
0x1800104cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104d4  lea     rsi, WPP_GLOBAL_Control
0x1800104db  cmp     rcx, rsi
0x1800104de  jz      loc_1800106BA
0x1800104e4  test    [rcx+44h], bl
0x1800104e7  jz      loc_1800106BA
0x1800104ed  lea     edx, [rbx+1Dh]
0x1800104f0  jmp     loc_18001065E
0x1800104f5  lea     rdx, aBufferunderrun; "BufferUnderrunFreeCapable"
0x1800104fc  mov     rcx, rbx; String1
0x1800104ff  call    wcscmp_0
0x180010504  test    eax, eax
0x180010506  jnz     short loc_180010573
0x180010508  mov     [rbp+57h+var_88], eax
0x18001050b  lea     r9, [rbp+57h+pvar]
0x18001050f  lea     rax, aBufferunderrun; "BufferUnderrunFreeCapable"
0x180010516  mov     edx, 1
0x18001051b  mov     [rbp+57h+var_80], rax
0x18001051f  lea     r8, [rbp+57h+var_88]
0x180010523  mov     rax, [r15]
0x180010526  mov     rcx, r15
0x180010529  mov     rax, [rax+18h]
0x18001052d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010532  movzx   ebx, r14b
0x180010536  lea     rcx, [rsi+48h]
0x18001053a  mov     r14d, 1
0x180010540  lea     r8, [rbp+57h+arg_0]
0x180010544  test    eax, eax
0x180010546  cmovs   ebx, r14d
0x18001054a  lea     edx, [r14+3]
0x18001054e  call    WriterGetProperty
0x180010553  mov     edi, eax
0x180010555  movzx   eax, bl
0x180010558  test    edi, edi
0x18001055a  cmovs   eax, r14d
0x18001055e  movzx   ecx, al
0x180010561  mov     eax, dword ptr [rbp+57h+pvar+8]
0x180010564  cmp     [rbp+57h+arg_0], eax
0x180010567  cmovnz  ecx, r14d
0x18001056b  mov     r14b, cl
0x18001056e  jmp     loc_180010620
0x180010573  lea     rdx, aEnablebufferun; "EnableBufferUnderrunFree"
0x18001057a  mov     rcx, rbx; String1
0x18001057d  call    wcscmp_0
0x180010582  test    eax, eax
0x180010584  jnz     loc_180010630
0x18001058a  mov     [rbp+57h+var_88], eax
0x18001058d  lea     r9, [rbp+57h+pvar]
0x180010591  lea     rax, aEnablebufferun; "EnableBufferUnderrunFree"
0x180010598  mov     ebx, 1
0x18001059d  mov     [rbp+57h+var_80], rax
0x1800105a1  lea     r8, [rbp+57h+var_88]
0x1800105a5  mov     rax, [r15]
0x1800105a8  mov     edx, ebx
0x1800105aa  mov     rcx, r15
0x1800105ad  mov     rax, [rax+18h]
0x1800105b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105b6  mov     edi, eax
0x1800105b8  test    eax, eax
0x1800105ba  js      loc_1800106B3
0x1800105c0  lea     eax, [rbx+2]
0x1800105c3  cmp     word ptr [rbp+57h+pvar], ax
0x1800105c7  jnz     short loc_18001061D
0x1800105c9  mov     r8d, dword ptr [rbp+57h+pvar+8]
0x1800105cd  lea     eax, [r8+1]
0x1800105d1  cmp     eax, 2
0x1800105d4  ja      short loc_18001061D
0x1800105d6  lea     rcx, [rsi+48h]
0x1800105da  lea     edx, [rbx+4]
0x1800105dd  call    WriterSetProperty
0x1800105e2  mov     edi, eax
0x1800105e4  test    eax, eax
0x1800105e6  js      loc_180010670
0x1800105ec  mov     rcx, [rsi+80h]
0x1800105f3  lea     r9, [rbp+57h+pvar]
0x1800105f7  lea     r8, [rbp+57h+var_88]
0x1800105fb  mov     [rsp+0D0h+var_B0], 2
0x180010603  mov     edx, ebx
0x180010605  mov     rax, [rcx]
0x180010608  mov     rax, [rax+20h]
  ... truncated ...
```
