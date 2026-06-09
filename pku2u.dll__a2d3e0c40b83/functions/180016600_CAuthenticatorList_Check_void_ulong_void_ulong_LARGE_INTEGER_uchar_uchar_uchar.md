# CAuthenticatorList::Check(void *,ulong,void *,ulong,_LARGE_INTEGER *,uchar,uchar,uchar)

- ea: `0x180016600`
- end: `0x180016854`
- name: `?Check@CAuthenticatorList@@QEAAJPEAXK0KPEAT_LARGE_INTEGER@@EEE@Z`
- size: `596`
- prototype: `__int64 __usercall@<rax>(PRTL_GENERIC_TABLE Table@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, union _LARGE_INTEGER *, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e900`

## callees

- `0x180016600`
- `0x1800179f0`
- `0x1800210f0`
- `0x180023cb8`
- `0x18002fca8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016643`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016643`
- `ntdll!RtlLeaveCriticalSection` at `0x180016829`
- `ntdll!RtlLeaveCriticalSection` at `0x180016829`
- `ntdll!RtlEnterCriticalSection` at `0x180016695`
- `ntdll!RtlEnterCriticalSection` at `0x180016695`
- `ntdll!RtlInsertElementGenericTable` at `0x180016784`
- `ntdll!RtlInsertElementGenericTable` at `0x180016784`
- `bcrypt!BCryptFinishHash` at `0x180016733`
- `bcrypt!BCryptFinishHash` at `0x180016733`
- `bcrypt!BCryptCreateHash` at `0x1800166ff`
- `bcrypt!BCryptCreateHash` at `0x1800166ff`
- `bcrypt!BCryptDestroyHash` at `0x180016749`
- `bcrypt!BCryptDestroyHash` at `0x180016749`

## pseudocode

```c
__int64 __fastcall CAuthenticatorList::Check(
        PRTL_GENERIC_TABLE Table,
        void *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        union _LARGE_INTEGER *a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        unsigned __int8 a9)
{
  PRTL_SPLAY_LINKS TableRoot; // rdx
  unsigned int v13; // ebx
  _DWORD *inserted; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned __int8 NewElement[4]; // [rsp+40h] [rbp-A8h] BYREF
  int v19; // [rsp+44h] [rbp-A4h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-A0h] BYREF
  union _LARGE_INTEGER v21; // [rsp+50h] [rbp-98h] BYREF
  union _LARGE_INTEGER v22; // [rsp+58h] [rbp-90h] BYREF
  struct _LIST_ENTRY **p_Blink; // [rsp+60h] [rbp-88h]
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+68h] [rbp-80h] BYREF
  _OWORD Buffer[2]; // [rsp+80h] [rbp-68h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  TableRoot = Table[1].TableRoot;
  v22.QuadPart = *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot;
  v21.QuadPart = (LONGLONG)TableRoot + *(_QWORD *)&SystemTimeAsFileTime;
  if ( a6->QuadPart < *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot
    || (v13 = 0, a6->QuadPart > (__int64)TableRoot + *(_QWORD *)&SystemTimeAsFileTime) )
  {
    v13 = 37;
  }
  if ( a9 )
  {
    p_Blink = &Table[1].InsertOrderList.Blink;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
    CAuthenticatorList::Age(Table, &v22, &v21);
    NewElement[0] = 0;
    memset(Buffer, 0, sizeof(Buffer));
    memset(phHash, 0, sizeof(phHash));
    *(union _LARGE_INTEGER *)&Buffer[0] = *a6;
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    CngRsa32Compat_MD5Update(phHash, a2, a3);
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash[0]);
    phHash[0] = 0;
    *(_OWORD *)((char *)Buffer + 12) = *(_OWORD *)&phHash[1];
    inserted = RtlInsertElementGenericTable(Table, Buffer, 0x20u, NewElement);
    if ( inserted )
    {
      if ( NewElement[0] )
      {
        inserted[2] = 1;
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_22;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v16 = 10;
      }
      else
      {
        if ( ++inserted[2] < LODWORD(Table[1].InsertOrderList.Flink) )
          goto LABEL_22;
        v13 = 34;
        v19 = 34;
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_22;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v16 = 11;
      }
      WPP_SF_(v15[2], v16, WPP_3e22fa556ccf3fdc813116008b3cc117_Traceguids);
    }
    else
    {
      v13 = 60;
      v19 = 60;
    }
LABEL_22:
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
  }
  return v13;
}

```

## disassembly

```asm
0x180016600  push    rbx
0x180016602  push    rsi
0x180016603  push    rdi
0x180016604  push    r12
0x180016606  push    r13
0x180016608  push    r14
0x18001660a  push    r15
0x18001660c  sub     rsp, 0B0h
0x180016613  mov     rax, cs:__security_cookie
0x18001661a  xor     rax, rsp
0x18001661d  mov     [rsp+0E8h+var_48], rax
0x180016625  mov     r15d, r8d
0x180016628  mov     r14, rdx
0x18001662b  mov     rdi, rcx
0x18001662e  mov     rsi, [rsp+0E8h+arg_28]
0x180016636  xor     r13d, r13d
0x180016639  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18001663e  lea     rcx, [rsp+0E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016643  call    cs:__imp_GetSystemTimeAsFileTime
0x180016649  mov     rdx, [rdi+48h]
0x18001664d  mov     rax, qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x180016652  mov     rcx, rax
0x180016655  sub     rcx, rdx
0x180016658  mov     qword ptr [rsp+0E8h+var_90], rcx
0x18001665d  lea     r8, [rdx+rax]
0x180016661  mov     qword ptr [rsp+0E8h+var_98], r8
0x180016666  mov     rax, [rsi]
0x180016669  cmp     rax, rcx
0x18001666c  jl      short loc_180016676
0x18001666e  mov     ebx, r13d
0x180016671  cmp     rax, r8
0x180016674  jle     short loc_18001667B
0x180016676  mov     ebx, 25h ; '%'
0x18001667b  cmp     [rsp+0E8h+arg_40], r13b
0x180016683  jz      loc_18001682F
0x180016689  lea     r12, [rdi+58h]
0x18001668d  mov     [rsp+0E8h+var_88], r12
0x180016692  mov     rcx, r12; CriticalSection
0x180016695  call    cs:__imp_RtlEnterCriticalSection
0x18001669b  nop
0x18001669c  lea     r8, [rsp+0E8h+var_98]; union _LARGE_INTEGER *
0x1800166a1  lea     rdx, [rsp+0E8h+var_90]; union _LARGE_INTEGER *
0x1800166a6  mov     rcx, rdi; Table
0x1800166a9  call    ?Age@CAuthenticatorList@@AEAAKAEBT_LARGE_INTEGER@@0@Z; CAuthenticatorList::Age(_LARGE_INTEGER const &,_LARGE_INTEGER const &)
0x1800166ae  mov     [rsp+0E8h+NewElement], 0
0x1800166b3  xorps   xmm0, xmm0
0x1800166b6  movups  [rsp+0E8h+Buffer], xmm0
0x1800166be  movups  [rsp+0E8h+var_58], xmm0
0x1800166c6  xorps   xmm1, xmm1
0x1800166c9  xor     eax, eax
0x1800166cb  movups  xmmword ptr [rsp+0E8h+phHash], xmm1
0x1800166d0  mov     qword ptr [rsp+0E8h+phHash+10h], rax
0x1800166d5  mov     rax, [rsi]
0x1800166d8  mov     qword ptr [rsp+0E8h+Buffer], rax
0x1800166e0  mov     [rsp+0E8h+dwFlags], r13d; dwFlags
0x1800166e5  mov     [rsp+0E8h+cbSecret], r13d; cbSecret
0x1800166ea  mov     [rsp+0E8h+pbSecret], r13; pbSecret
0x1800166ef  xor     r9d, r9d; cbHashObject
0x1800166f2  xor     r8d, r8d; pbHashObject
0x1800166f5  lea     rdx, [rsp+0E8h+phHash]; phHash
0x1800166fa  mov     ecx, 21h ; '!'; hAlgorithm
0x1800166ff  call    cs:__imp_BCryptCreateHash
0x180016705  test    eax, eax
0x180016707  jns     short loc_180016710
0x180016709  mov     ecx, 7
0x18001670e  int     29h; Win8: RtlFailFast(ecx)
0x180016710  mov     r8d, r15d
0x180016713  mov     rdx, r14
0x180016716  lea     rcx, [rsp+0E8h+phHash]
0x18001671b  call    CngRsa32Compat_MD5Update
0x180016720  xor     r9d, r9d; dwFlags
0x180016723  mov     r8d, 10h; cbOutput
0x180016729  lea     rdx, [rsp+0E8h+phHash+8]; pbOutput
0x18001672e  mov     rcx, qword ptr [rsp+0E8h+phHash]; hHash
0x180016733  call    cs:__imp_BCryptFinishHash
0x180016739  test    eax, eax
0x18001673b  jns     short loc_180016744
0x18001673d  mov     ecx, 7
0x180016742  int     29h; Win8: RtlFailFast(ecx)
0x180016744  mov     rcx, qword ptr [rsp+0E8h+phHash]; hHash
0x180016749  call    cs:__imp_BCryptDestroyHash
0x18001674f  mov     qword ptr [rsp+0E8h+phHash], r13
0x180016754  mov     rax, qword ptr [rsp+0E8h+phHash+8]
0x180016759  mov     qword ptr [rsp+0E8h+Buffer+0Ch], rax
0x180016761  mov     rax, qword ptr [rsp+0E8h+phHash+10h]
0x180016766  mov     qword ptr [rsp+0E8h+var_58+4], rax
0x18001676e  lea     r9, [rsp+0E8h+NewElement]; NewElement
0x180016773  mov     r8d, 20h ; ' '; BufferSize
0x180016779  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x180016781  mov     rcx, rdi; Table
0x180016784  call    cs:__imp_RtlInsertElementGenericTable
0x18001678a  test    rax, rax
0x18001678d  jnz     short loc_18001679A
0x18001678f  mov     ebx, 3Ch ; '<'
0x180016794  mov     [rsp+0E8h+var_A4], ebx
0x180016798  jmp     short loc_180016816
0x18001679a  cmp     [rsp+0E8h+NewElement], 0
0x18001679f  jz      short loc_1800167CE
0x1800167a1  mov     dword ptr [rax+8], 1
0x1800167a8  cmp     byte ptr [rdi+54h], 0
0x1800167ac  jz      short loc_180016816
0x1800167ae  lea     rax, WPP_GLOBAL_Control
0x1800167b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167bc  cmp     rcx, rax
0x1800167bf  jz      short loc_180016816
0x1800167c1  test    byte ptr [rcx+1Ch], 1
0x1800167c5  jz      short loc_180016816
0x1800167c7  mov     edx, 0Ah
0x1800167cc  jmp     short loc_180016806
0x1800167ce  inc     dword ptr [rax+8]
0x1800167d1  mov     eax, [rax+8]
0x1800167d4  cmp     eax, [rdi+50h]
0x1800167d7  jb      short loc_180016816
0x1800167d9  mov     ebx, 22h ; '"'
0x1800167de  mov     [rsp+0E8h+var_A4], ebx
0x1800167e2  cmp     byte ptr [rdi+54h], 0
0x1800167e6  jz      short loc_180016816
0x1800167e8  lea     rax, WPP_GLOBAL_Control
0x1800167ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167f6  cmp     rcx, rax
0x1800167f9  jz      short loc_180016816
0x1800167fb  test    byte ptr [rcx+1Ch], 1
0x1800167ff  jz      short loc_180016816
0x180016801  mov     edx, 0Bh
0x180016806  lea     r8, WPP_3e22fa556ccf3fdc813116008b3cc117_Traceguids
0x18001680d  mov     rcx, [rcx+10h]
0x180016811  call    WPP_SF_
0x180016816  jmp     short loc_180016826
0x180016818  mov     ebx, 3Ch ; '<'
0x18001681d  mov     [rsp+0E8h+var_A4], ebx
0x180016821  mov     r12, [rsp+0E8h+var_88]
0x180016826  mov     rcx, r12; CriticalSection
0x180016829  call    cs:__imp_RtlLeaveCriticalSection
0x18001682f  mov     eax, ebx
0x180016831  mov     rcx, [rsp+0E8h+var_48]
0x180016839  xor     rcx, rsp; StackCookie
0x18001683c  call    __security_check_cookie
0x180016841  add     rsp, 0B0h
0x180016848  pop     r15
0x18001684a  pop     r14
0x18001684c  pop     r13
0x18001684e  pop     r12
0x180016850  pop     rdi
0x180016851  pop     rsi
0x180016852  pop     rbx
0x180016853  retn
```
