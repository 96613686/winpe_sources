# Array<uchar *>::setSize(uint)

- ea: `0x1800191e8`
- end: `0x180019329`
- name: `?setSize@?$Array@PEAE@@QEAAXI@Z`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800191ac`

## callees

- `0x180005944`
- `0x180007364`
- `0x1800191e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019295`

## string_xrefs

- `0x1800192c1`: `com\complus\src\inc\svcmem.h`
- `0x18001925f`: `com\complus\src\inc\array_t.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Array<unsigned char *>::setSize(__int64 a1, unsigned int a2)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rsi
  DWORD LastError; // eax
  unsigned __int16 v6; // r8
  unsigned int v7; // r9d
  _QWORD *v8; // rax
  __int64 i; // rdx
  const void *v10; // [rsp+28h] [rbp-21h]
  unsigned int v11; // [rsp+30h] [rbp-19h]
  int v12; // [rsp+38h] [rbp-11h]
  int v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+50h] [rbp+7h] BYREF
  __int16 v15; // [rsp+54h] [rbp+Bh]
  int v16; // [rsp+58h] [rbp+Fh]
  unsigned __int16 *v17; // [rsp+60h] [rbp+17h]
  __int64 v18; // [rsp+68h] [rbp+1Fh]
  __int64 v19; // [rsp+70h] [rbp+27h]
  int v20; // [rsp+78h] [rbp+2Fh]
  int v21; // [rsp+7Ch] [rbp+33h]

  if ( a2 > dword_1800733DC )
  {
    v3 = (unsigned int)(3 * dword_1800733DC) >> 1;
    if ( a2 > v3 )
      v3 = a2;
    if ( v3 > 0x20000000 )
    {
      v14 = 0;
      v15 = 21;
      v16 = -1073605930;
      v17 = L"itMaxNew <= itMaxMax";
      v18 = 0;
      v19 = 0;
      v21 = 1;
      v20 = 1;
      CError::WriteToLog((CError *)&v14, L"com\\complus\\src\\inc\\array_t.h", 0x93u, L"itMaxNew <= itMaxMax");
    }
    v4 = CoTaskMemAlloc(saturated_mul(v3, 8u));
    if ( !v4 )
    {
      LastError = GetLastError();
      CErrorWin32::CErrorWin32((CErrorWin32 *)&v14, LastError, v6, v7, L"Out of memory", v10, v11, v12, v13);
      v20 = 1;
      CError::WriteToLog((CError *)&v14, L"com\\complus\\src\\inc\\svcmem.h", 0x39u, v17);
    }
    v8 = CCheckGroupMembership::sm_apSid;
    if ( CCheckGroupMembership::sm_apSid )
    {
      for ( i = 0; (unsigned int)i < dword_1800733D8; v8 = CCheckGroupMembership::sm_apSid )
      {
        v4[i] = v8[i];
        i = (unsigned int)(i + 1);
      }
      CoTaskMemFree(v8);
    }
    CCheckGroupMembership::sm_apSid = v4;
    dword_1800733DC = v3;
  }
  dword_1800733D8 = a2;
}

```

## disassembly

```asm
0x1800191e8  push    rbp
0x1800191ea  push    rbx
0x1800191eb  push    rsi
0x1800191ec  push    rdi
0x1800191ed  lea     rbp, [rsp-3Fh]
0x1800191f2  sub     rsp, 88h
0x1800191f9  mov     edi, edx
0x1800191fb  mov     eax, cs:dword_1800733DC
0x180019201  cmp     edx, eax
0x180019203  jbe     loc_180019317
0x180019209  lea     ebx, [rax+rax*2]
0x18001920c  shr     ebx, 1
0x18001920e  cmp     edx, ebx
0x180019210  cmova   ebx, edx
0x180019213  cmp     ebx, 20000000h
0x180019219  jbe     short loc_18001926F
0x18001921b  mov     [rbp+57h+var_50], 0
0x180019222  mov     eax, 15h
0x180019227  mov     [rbp+57h+var_4C], ax
0x18001922b  mov     [rbp+57h+var_48], 0C00212D6h
0x180019232  lea     r9, aItmaxnewItmaxm; "itMaxNew <= itMaxMax"
0x180019239  mov     [rbp+57h+var_40], r9
0x18001923d  mov     [rbp+57h+var_38], 0
0x180019245  mov     [rbp+57h+var_30], 0
0x18001924d  mov     [rbp+57h+var_24], 1
0x180019254  mov     [rbp+57h+var_28], 1
0x18001925b  lea     r8d, [rax+7Eh]; unsigned int
0x18001925f  lea     rdx, aComComplusSrcI_1; "com\\complus\\src\\inc\\array_t.h"
0x180019266  lea     rcx, [rbp+57h+var_50]; this
0x18001926a  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18001926f  mov     ecx, ebx
0x180019271  mov     eax, 8
0x180019276  mul     rcx
0x180019279  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019280  cmovb   rax, rcx
0x180019284  mov     rcx, rax; cb
0x180019287  call    cs:__imp_CoTaskMemAlloc
0x18001928d  mov     rsi, rax
0x180019290  test    rax, rax
0x180019293  jnz     short loc_1800192D1
0x180019295  call    cs:__imp_GetLastError
0x18001929b  mov     edx, eax; unsigned int
0x18001929d  lea     rax, aOutOfMemory; "Out of memory"
0x1800192a4  mov     [rsp+0A0h+var_80], rax; unsigned __int16 *
0x1800192a9  lea     rcx, [rbp+57h+var_50]; this
0x1800192ad  call    ??0CErrorWin32@@QEAA@KGKPEBGPEBXIHH@Z; CErrorWin32::CErrorWin32(ulong,ushort,ulong,ushort const *,void const *,uint,int,int)
0x1800192b2  mov     [rbp+57h+var_28], 1
0x1800192b9  mov     r9, [rbp+57h+var_40]; unsigned __int16 *
0x1800192bd  lea     r8d, [rsi+39h]; unsigned int
0x1800192c1  lea     rdx, aComComplusSrcI_0; "com\\complus\\src\\inc\\svcmem.h"
0x1800192c8  lea     rcx, [rbp+57h+var_50]; this
0x1800192cc  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800192d1  mov     rax, cs:?sm_apSid@CCheckGroupMembership@@0V?$Array@PEAE@@A; Array<uchar *> CCheckGroupMembership::sm_apSid
0x1800192d8  test    rax, rax
0x1800192db  jz      short loc_18001930A
0x1800192dd  xor     edx, edx
0x1800192df  cmp     cs:dword_1800733D8, edx
0x1800192e5  jbe     short loc_180019300
0x1800192e7  mov     rax, [rax+rdx*8]
0x1800192eb  mov     [rsi+rdx*8], rax
0x1800192ef  inc     edx
0x1800192f1  mov     rax, cs:?sm_apSid@CCheckGroupMembership@@0V?$Array@PEAE@@A; Array<uchar *> CCheckGroupMembership::sm_apSid
0x1800192f8  cmp     edx, cs:dword_1800733D8
0x1800192fe  jb      short loc_1800192E7
0x180019300  mov     rcx, rax; pv
0x180019303  call    cs:__imp_CoTaskMemFree
0x180019309  nop
0x18001930a  mov     cs:?sm_apSid@CCheckGroupMembership@@0V?$Array@PEAE@@A, rsi; Array<uchar *> CCheckGroupMembership::sm_apSid
0x180019311  mov     cs:dword_1800733DC, ebx
0x180019317  mov     cs:dword_1800733D8, edi
0x18001931d  add     rsp, 88h
0x180019324  pop     rdi
0x180019325  pop     rsi
0x180019326  pop     rbx
0x180019327  pop     rbp
0x180019328  retn
```
