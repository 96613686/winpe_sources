# CFilteringPlatformHelperClass::LowHealth(ushort const *,ushort * *,long *,tagDIAGNOSIS_STATUS *)

- ea: `0x180008540`
- end: `0x180008722`
- name: `?LowHealth@CFilteringPlatformHelperClass@@UEAAJPEBGPEAPEAGPEAJPEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(struct _FILETIME *this, const unsigned __int16 *, unsigned __int16 **, int *, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008540`
- `0x180008b74`
- `0x18000934c`
- `0x18000c63c`
- `0x180011302`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000869d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000869d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800085b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800085b3`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::LowHealth(
        struct _FILETIME *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        int *a4,
        enum tagDIAGNOSIS_STATUS *a5)
{
  enum tagDIAGNOSIS_STATUS *v5; // rsi
  int Attributes; // eax
  int IsNonNAPCertMMSaPresent; // ecx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  struct _FILETIME v12; // rbx
  void *v13; // rcx
  LPVOID pv; // [rsp+20h] [rbp-B8h] BYREF
  int v16; // [rsp+28h] [rbp-B0h]
  LPVOID v17; // [rsp+30h] [rbp-A8h]
  void *v18; // [rsp+38h] [rbp-A0h]
  char v19; // [rsp+F0h] [rbp+18h] BYREF

  v5 = a5;
  *a3 = 0;
  v19 = 0;
  *v5 = DS_REJECTED;
  Attributes = CFilteringPlatformHelperClass::loadAttributes((CFilteringPlatformHelperClass *)this);
  IsNonNAPCertMMSaPresent = Attributes;
  if ( Attributes == -2147024809 )
    return 0;
  if ( Attributes >= 0 )
  {
    if ( this[54] )
    {
      *v5 = DS_PASSTHROUGH;
      return (unsigned int)IsNonNAPCertMMSaPresent;
    }
    if ( !LOBYTE(this[58].dwLowDateTime) )
    {
      GetSystemTimeAsFileTime(this + 57);
      v10 = (unsigned __int64)this[57];
      if ( v10 <= 0x165A0BC00LL )
        v11 = 0;
      else
        v11 = v10 - 6000000000LL;
      this[56] = (struct _FILETIME)v11;
      LOBYTE(this[58].dwLowDateTime) = 1;
    }
    IsNonNAPCertMMSaPresent = CFilteringPlatformHelperClass::checkFailureEvents(
                                (CFilteringPlatformHelperClass *)this,
                                v5,
                                a3);
    if ( IsNonNAPCertMMSaPresent >= 0 )
    {
      if ( *v5 == DS_REJECTED )
      {
        IsNonNAPCertMMSaPresent = FwhcIsNonNAPCertMMSaPresent(
                                    *(_QWORD *)&this[52],
                                    *(_QWORD *)&this[17],
                                    *(_QWORD *)&this[18],
                                    &v19);
        if ( IsNonNAPCertMMSaPresent < 0 )
          return (unsigned int)IsNonNAPCertMMSaPresent;
        if ( v19 )
        {
          *v5 = DS_INDETERMINATE;
          LOBYTE(this[65].dwLowDateTime) = 1;
        }
      }
      v12 = this[55];
      if ( !*(_QWORD *)&v12 )
        goto LABEL_27;
      memset_0(&pv, 0, 0x90u);
      if ( (*(int (__fastcall **)(struct _FILETIME, const wchar_t *, LPVOID *))(**(_QWORD **)&v12 + 32LL))(
             v12,
             L"isinboundscenario",
             &pv) >= 0 )
      {
        if ( (_DWORD)v17 && *v5 == DS_REJECTED )
          *v5 = DS_INDETERMINATE;
        CoTaskMemFree(pv);
        pv = 0;
        if ( v16 == 10 )
        {
          v13 = v17;
          goto LABEL_25;
        }
        if ( v16 == 14 )
        {
          v13 = v18;
LABEL_25:
          CoTaskMemFree(v13);
        }
      }
      IsNonNAPCertMMSaPresent = 0;
LABEL_27:
      if ( LOBYTE(this[61].dwLowDateTime)
        && this[61].dwHighDateTime == 1259681589
        && this[62].dwLowDateTime == 1149243465
        && this[62].dwHighDateTime == -1177439062
        && this[63].dwLowDateTime == 272089277 )
      {
        *v5 = DS_REJECTED;
      }
    }
  }
  return (unsigned int)IsNonNAPCertMMSaPresent;
}

```

## disassembly

```asm
0x180008540  mov     rax, rsp
0x180008543  push    rbx
0x180008544  push    rsi
0x180008545  push    rdi
0x180008546  push    r14
0x180008548  sub     rsp, 0B8h
0x18000854f  mov     rsi, [rsp+0D8h+arg_20]
0x180008557  mov     r14, r8
0x18000855a  mov     qword ptr [r8], 0
0x180008561  mov     rdi, rcx
0x180008564  mov     byte ptr [rax+18h], 0
0x180008568  mov     dword ptr [rsi], 2
0x18000856e  call    ?loadAttributes@CFilteringPlatformHelperClass@@AEAAJXZ; CFilteringPlatformHelperClass::loadAttributes(void)
0x180008573  mov     ecx, eax
0x180008575  cmp     eax, 80070057h
0x18000857a  jnz     short loc_180008583
0x18000857c  xor     ecx, ecx
0x18000857e  jmp     loc_180008713
0x180008583  test    eax, eax
0x180008585  js      loc_180008713
0x18000858b  cmp     qword ptr [rdi+1B0h], 0
0x180008593  jz      short loc_1800085A0
0x180008595  mov     dword ptr [rsi], 5
0x18000859b  jmp     loc_180008713
0x1800085a0  cmp     byte ptr [rdi+1D0h], 0
0x1800085a7  jnz     short loc_1800085E9
0x1800085a9  lea     rbx, [rdi+1C8h]
0x1800085b0  mov     rcx, rbx; lpSystemTimeAsFileTime
0x1800085b3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800085b9  mov     rax, [rbx]
0x1800085bc  mov     rcx, 165A0BC00h
0x1800085c6  cmp     rax, rcx
0x1800085c9  jbe     short loc_1800085D0
0x1800085cb  sub     rax, rcx
0x1800085ce  jmp     short loc_1800085D2
0x1800085d0  xor     eax, eax
0x1800085d2  mov     [rdi+1C0h], eax
0x1800085d8  shr     rax, 20h
0x1800085dc  mov     [rdi+1C4h], eax
0x1800085e2  mov     byte ptr [rdi+1D0h], 1
0x1800085e9  mov     r8, r14; unsigned __int16 **
0x1800085ec  mov     rdx, rsi; enum tagDIAGNOSIS_STATUS *
0x1800085ef  mov     rcx, rdi; this
0x1800085f2  call    ?checkFailureEvents@CFilteringPlatformHelperClass@@AEAAJPEAW4tagDIAGNOSIS_STATUS@@PEAPEAG@Z; CFilteringPlatformHelperClass::checkFailureEvents(tagDIAGNOSIS_STATUS *,ushort * *)
0x1800085f7  mov     ecx, eax
0x1800085f9  test    eax, eax
0x1800085fb  js      loc_180008713
0x180008601  cmp     dword ptr [rsi], 2
0x180008604  mov     r14d, 3
0x18000860a  jnz     short loc_18000864C
0x18000860c  mov     r8, [rdi+90h]
0x180008613  lea     r9, [rsp+0D8h+arg_10]
0x18000861b  mov     rdx, [rdi+88h]
0x180008622  mov     rcx, [rdi+1A0h]
0x180008629  call    FwhcIsNonNAPCertMMSaPresent
0x18000862e  mov     ecx, eax
0x180008630  test    eax, eax
0x180008632  js      loc_180008713
0x180008638  cmp     [rsp+0D8h+arg_10], 0
0x180008640  jz      short loc_18000864C
0x180008642  mov     [rsi], r14d
0x180008645  mov     byte ptr [rdi+208h], 1
0x18000864c  mov     rbx, [rdi+1B8h]
0x180008653  test    rbx, rbx
0x180008656  jz      short loc_1800086CE
0x180008658  xor     edx, edx; Val
0x18000865a  lea     rcx, [rsp+0D8h+pv]; void *
0x18000865f  mov     r8d, 90h; Size
0x180008665  call    memset_0
0x18000866a  mov     rax, [rbx]
0x18000866d  lea     r8, [rsp+0D8h+pv]
0x180008672  lea     rdx, aIsinboundscena; "isinboundscenario"
0x180008679  mov     rcx, rbx
0x18000867c  mov     rax, [rax+20h]
0x180008680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008685  test    eax, eax
0x180008687  js      short loc_1800086CC
0x180008689  cmp     dword ptr [rsp+0D8h+var_A8], 0
0x18000868e  jz      short loc_180008698
0x180008690  cmp     dword ptr [rsi], 2
0x180008693  jnz     short loc_180008698
0x180008695  mov     [rsi], r14d
0x180008698  mov     rcx, [rsp+0D8h+pv]; pv
0x18000869d  call    cs:__imp_CoTaskMemFree
0x1800086a3  cmp     [rsp+0D8h+var_B0], 0Ah
0x1800086a8  mov     [rsp+0D8h+pv], 0
0x1800086b1  jz      short loc_1800086C1
0x1800086b3  cmp     [rsp+0D8h+var_B0], 0Eh
0x1800086b8  jnz     short loc_1800086CC
0x1800086ba  mov     rcx, [rsp+0D8h+var_A0]
0x1800086bf  jmp     short loc_1800086C6
0x1800086c1  mov     rcx, [rsp+0D8h+var_A8]; pv
0x1800086c6  call    cs:__imp_CoTaskMemFree
0x1800086cc  xor     ecx, ecx
0x1800086ce  cmp     byte ptr [rdi+1E8h], 0
0x1800086d5  jz      short loc_180008713
0x1800086d7  cmp     dword ptr [rdi+1ECh], 4B153735h
0x1800086e1  jnz     short loc_180008713
0x1800086e3  mov     eax, cs:dword_18001651C
0x1800086e9  cmp     eax, [rdi+1F0h]
0x1800086ef  jnz     short loc_180008713
0x1800086f1  mov     eax, cs:dword_180016520
0x1800086f7  cmp     eax, [rdi+1F4h]
0x1800086fd  jnz     short loc_180008713
0x1800086ff  mov     eax, cs:dword_180016524
0x180008705  cmp     eax, [rdi+1F8h]
0x18000870b  jnz     short loc_180008713
0x18000870d  mov     dword ptr [rsi], 2
0x180008713  mov     eax, ecx
0x180008715  add     rsp, 0B8h
0x18000871c  pop     r14
0x18000871e  pop     rdi
0x18000871f  pop     rsi
0x180008720  pop     rbx
0x180008721  retn
```
