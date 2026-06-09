# CAuthenticatorList::Check(void *,ulong,void *,ulong,_LARGE_INTEGER *,uchar,uchar,uchar)

- ea: `0x180030774`
- end: `0x180030a0b`
- name: `?Check@CAuthenticatorList@@QEAAJPEAXK0KPEAT_LARGE_INTEGER@@EEE@Z`
- size: `663`
- prototype: `__int64 __usercall@<rax>(PRTL_GENERIC_TABLE Table@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, union _LARGE_INTEGER *, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004a20`

## callees

- `0x180030774`
- `0x18006d73c`
- `0x180070680`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800307bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800307bc`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003083a`
- `ntdll!RtlDeleteElementGenericTable` at `0x18003083a`
- `ntdll!RtlInsertElementGenericTable` at `0x18003093e`
- `ntdll!RtlInsertElementGenericTable` at `0x18003093e`
- `ntdll!RtlGetElementGenericTable` at `0x18003081f`
- `ntdll!RtlGetElementGenericTable` at `0x18003081f`
- `ntdll!RtlEnterCriticalSection` at `0x180030802`
- `ntdll!RtlEnterCriticalSection` at `0x180030814`
- `ntdll!RtlEnterCriticalSection` at `0x180030802`
- `ntdll!RtlEnterCriticalSection` at `0x180030814`
- `ntdll!RtlLeaveCriticalSection` at `0x180030856`
- `ntdll!RtlLeaveCriticalSection` at `0x1800309e0`
- `ntdll!RtlLeaveCriticalSection` at `0x180030856`
- `ntdll!RtlLeaveCriticalSection` at `0x1800309e0`
- `bcrypt!BCryptCreateHash` at `0x1800308ac`
- `bcrypt!BCryptCreateHash` at `0x1800308ac`
- `bcrypt!BCryptHashData` at `0x1800308cf`
- `bcrypt!BCryptHashData` at `0x1800308cf`
- `bcrypt!BCryptDestroyHash` at `0x180030903`
- `bcrypt!BCryptDestroyHash` at `0x180030903`
- `bcrypt!BCryptFinishHash` at `0x1800308ef`
- `bcrypt!BCryptFinishHash` at `0x1800308ef`

## pseudocode

```c
__int64 __fastcall CAuthenticatorList::Check(
        PRTL_GENERIC_TABLE Table,
        UCHAR *a2,
        ULONG a3,
        void *a4,
        unsigned int a5,
        union _LARGE_INTEGER *a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        unsigned __int8 a9)
{
  PRTL_SPLAY_LINKS TableRoot; // rdx
  LONGLONG v11; // rdi
  LONGLONG v12; // rbx
  unsigned int v13; // esi
  int v14; // r12d
  LONGLONG *ElementGenericTable; // rax
  int v16; // eax
  _DWORD *inserted; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned __int8 NewElement[4]; // [rsp+40h] [rbp-A8h] BYREF
  int v22; // [rsp+44h] [rbp-A4h]
  int v23; // [rsp+48h] [rbp-A0h]
  ULONG cbInput; // [rsp+4Ch] [rbp-9Ch]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-98h] BYREF
  PUCHAR pbInput; // [rsp+58h] [rbp-90h]
  struct _LIST_ENTRY **p_Blink; // [rsp+60h] [rbp-88h]
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+68h] [rbp-80h] BYREF
  _OWORD Buffer[2]; // [rsp+80h] [rbp-68h] BYREF

  cbInput = a3;
  pbInput = a2;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  TableRoot = Table[1].TableRoot;
  v11 = *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot;
  v12 = (LONGLONG)TableRoot + *(_QWORD *)&SystemTimeAsFileTime;
  if ( a6->QuadPart < *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot || (v13 = 0, a6->QuadPart > v12) )
    v13 = 37;
  if ( a9 )
  {
    p_Blink = &Table[1].InsertOrderList.Blink;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
    v14 = 0;
    v23 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
    do
    {
      ElementGenericTable = (LONGLONG *)RtlGetElementGenericTable(Table, 0);
      if ( ElementGenericTable && (*ElementGenericTable < v11 || *ElementGenericTable > v12) )
      {
        v16 = RtlDeleteElementGenericTable(Table, ElementGenericTable);
        v23 = ++v14;
      }
      else
      {
        v16 = 0;
      }
    }
    while ( v16 );
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
    NewElement[0] = 0;
    memset(Buffer, 0, sizeof(Buffer));
    memset(phHash, 0, sizeof(phHash));
    *(union _LARGE_INTEGER *)&Buffer[0] = *a6;
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], pbInput, cbInput, 0) < 0 )
      __fastfail(7u);
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
          goto LABEL_31;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_31;
        v19 = 10;
      }
      else
      {
        if ( ++inserted[2] < LODWORD(Table[1].InsertOrderList.Flink) )
          goto LABEL_31;
        v13 = 34;
        v22 = 34;
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_31;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_31;
        v19 = 11;
      }
      WPP_SF_(v18[2], v19, WPP_ca534e7a7fb3321a12b2f35c29d9b937_Traceguids);
    }
    else
    {
      v13 = 60;
      v22 = 60;
    }
LABEL_31:
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
  }
  return v13;
}

```

## disassembly

```asm
0x180030774  push    rbx
0x180030776  push    rsi
0x180030777  push    rdi
0x180030778  push    r12
0x18003077a  push    r13
0x18003077c  push    r14
0x18003077e  push    r15
0x180030780  sub     rsp, 0B0h
0x180030787  mov     rax, cs:__security_cookie
0x18003078e  xor     rax, rsp
0x180030791  mov     [rsp+0E8h+var_48], rax
0x180030799  mov     [rsp+0E8h+cbInput], r8d
0x18003079e  mov     [rsp+0E8h+pbInput], rdx
0x1800307a3  mov     r14, rcx
0x1800307a6  mov     r13, [rsp+0E8h+arg_28]
0x1800307ae  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800307b7  lea     rcx, [rsp+0E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800307bc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800307c2  mov     rdx, [r14+48h]
0x1800307c6  mov     rax, qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800307cb  mov     rdi, rax
0x1800307ce  sub     rdi, rdx
0x1800307d1  lea     rbx, [rdx+rax]
0x1800307d5  cmp     [r13+0], rdi
0x1800307d9  jl      short loc_1800307E3
0x1800307db  xor     esi, esi
0x1800307dd  cmp     [r13+0], rbx
0x1800307e1  jle     short loc_1800307E8
0x1800307e3  mov     esi, 25h ; '%'
0x1800307e8  cmp     [rsp+0E8h+arg_40], 0
0x1800307f0  jz      loc_1800309E6
0x1800307f6  lea     r15, [r14+58h]
0x1800307fa  mov     [rsp+0E8h+var_88], r15
0x1800307ff  mov     rcx, r15; CriticalSection
0x180030802  call    cs:__imp_RtlEnterCriticalSection
0x180030808  nop
0x180030809  xor     r12d, r12d
0x18003080c  mov     [rsp+0E8h+var_A0], r12d
0x180030811  mov     rcx, r15; CriticalSection
0x180030814  call    cs:__imp_RtlEnterCriticalSection
0x18003081a  xor     edx, edx; I
0x18003081c  mov     rcx, r14; Table
0x18003081f  call    cs:__imp_RtlGetElementGenericTable
0x180030825  test    rax, rax
0x180030828  jz      short loc_18003084D
0x18003082a  cmp     [rax], rdi
0x18003082d  jl      short loc_180030834
0x18003082f  cmp     [rax], rbx
0x180030832  jle     short loc_18003084D
0x180030834  mov     rdx, rax; Buffer
0x180030837  mov     rcx, r14; Table
0x18003083a  call    cs:__imp_RtlDeleteElementGenericTable
0x180030840  movzx   eax, al
0x180030843  inc     r12d
0x180030846  mov     [rsp+0E8h+var_A0], r12d
0x18003084b  jmp     short loc_18003084F
0x18003084d  xor     eax, eax
0x18003084f  test    eax, eax
0x180030851  jnz     short loc_18003081A
0x180030853  mov     rcx, r15; CriticalSection
0x180030856  call    cs:__imp_RtlLeaveCriticalSection
0x18003085c  xor     edi, edi
0x18003085e  mov     [rsp+0E8h+NewElement], dil
0x180030863  xorps   xmm0, xmm0
0x180030866  movups  [rsp+0E8h+Buffer], xmm0
0x18003086e  movups  [rsp+0E8h+var_58], xmm0
0x180030876  xorps   xmm1, xmm1
0x180030879  xor     eax, eax
0x18003087b  movups  xmmword ptr [rsp+0E8h+phHash], xmm1
0x180030880  mov     qword ptr [rsp+0E8h+phHash+10h], rax
0x180030885  mov     rax, [r13+0]
0x180030889  mov     qword ptr [rsp+0E8h+Buffer], rax
0x180030891  mov     [rsp+0E8h+dwFlags], edi; dwFlags
0x180030895  mov     [rsp+0E8h+cbSecret], edi; cbSecret
0x180030899  mov     [rsp+0E8h+pbSecret], rdi; pbSecret
0x18003089e  xor     r9d, r9d; cbHashObject
0x1800308a1  xor     r8d, r8d; pbHashObject
0x1800308a4  lea     rdx, [rsp+0E8h+phHash]; phHash
0x1800308a9  lea     ecx, [rdi+21h]; hAlgorithm
0x1800308ac  call    cs:__imp_BCryptCreateHash
0x1800308b2  lea     ebx, [rdi+7]
0x1800308b5  test    eax, eax
0x1800308b7  jns     short loc_1800308BD
0x1800308b9  mov     ecx, ebx
0x1800308bb  int     29h; Win8: RtlFailFast(ecx)
0x1800308bd  xor     r9d, r9d; dwFlags
0x1800308c0  mov     r8d, [rsp+0E8h+cbInput]; cbInput
0x1800308c5  mov     rdx, [rsp+0E8h+pbInput]; pbInput
0x1800308ca  mov     rcx, qword ptr [rsp+0E8h+phHash]; hHash
0x1800308cf  call    cs:__imp_BCryptHashData
0x1800308d5  test    eax, eax
0x1800308d7  jns     short loc_1800308DE
0x1800308d9  mov     rcx, rbx
0x1800308dc  int     29h; Win8: RtlFailFast(ecx)
0x1800308de  xor     r9d, r9d; dwFlags
0x1800308e1  lea     r8d, [r9+10h]; cbOutput
0x1800308e5  lea     rdx, [rsp+0E8h+phHash+8]; pbOutput
0x1800308ea  mov     rcx, qword ptr [rsp+0E8h+phHash]; hHash
0x1800308ef  call    cs:__imp_BCryptFinishHash
0x1800308f5  test    eax, eax
0x1800308f7  jns     short loc_1800308FE
0x1800308f9  mov     rcx, rbx
0x1800308fc  int     29h; Win8: RtlFailFast(ecx)
0x1800308fe  mov     rcx, qword ptr [rsp+0E8h+phHash]; hHash
0x180030903  call    cs:__imp_BCryptDestroyHash
0x180030909  mov     qword ptr [rsp+0E8h+phHash], rdi
0x18003090e  mov     rax, qword ptr [rsp+0E8h+phHash+8]
0x180030913  mov     qword ptr [rsp+0E8h+Buffer+0Ch], rax
0x18003091b  mov     rax, qword ptr [rsp+0E8h+phHash+10h]
0x180030920  mov     qword ptr [rsp+0E8h+var_58+4], rax
0x180030928  lea     r9, [rsp+0E8h+NewElement]; NewElement
0x18003092d  mov     r8d, 20h ; ' '; BufferSize
0x180030933  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x18003093b  mov     rcx, r14; Table
0x18003093e  call    cs:__imp_RtlInsertElementGenericTable
0x180030944  test    rax, rax
0x180030947  jnz     short loc_180030952
0x180030949  lea     esi, [rax+3Ch]
0x18003094c  mov     [rsp+0E8h+var_A4], esi
0x180030950  jmp     short loc_1800309CD
0x180030952  cmp     [rsp+0E8h+NewElement], dil
0x180030957  jz      short loc_180030986
0x180030959  mov     dword ptr [rax+8], 1
0x180030960  cmp     [r14+54h], dil
0x180030964  jz      short loc_1800309CD
0x180030966  lea     rax, WPP_GLOBAL_Control
0x18003096d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030974  cmp     rcx, rax
0x180030977  jz      short loc_1800309CD
0x180030979  test    byte ptr [rcx+1Ch], 1
0x18003097d  jz      short loc_1800309CD
0x18003097f  mov     edx, 0Ah
0x180030984  jmp     short loc_1800309BD
0x180030986  inc     dword ptr [rax+8]
0x180030989  mov     eax, [rax+8]
0x18003098c  cmp     eax, [r14+50h]
0x180030990  jb      short loc_1800309CD
0x180030992  mov     esi, 22h ; '"'
0x180030997  mov     [rsp+0E8h+var_A4], esi
0x18003099b  cmp     [r14+54h], dil
0x18003099f  jz      short loc_1800309CD
0x1800309a1  lea     rax, WPP_GLOBAL_Control
0x1800309a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309af  cmp     rcx, rax
0x1800309b2  jz      short loc_1800309CD
0x1800309b4  test    byte ptr [rcx+1Ch], 1
0x1800309b8  jz      short loc_1800309CD
0x1800309ba  lea     edx, [rsi-17h]
0x1800309bd  lea     r8, WPP_ca534e7a7fb3321a12b2f35c29d9b937_Traceguids
0x1800309c4  mov     rcx, [rcx+10h]
0x1800309c8  call    WPP_SF_
0x1800309cd  jmp     short loc_1800309DD
0x1800309cf  mov     esi, 3Ch ; '<'
0x1800309d4  mov     [rsp+0E8h+var_A4], esi
0x1800309d8  mov     r15, [rsp+0E8h+var_88]
0x1800309dd  mov     rcx, r15; CriticalSection
0x1800309e0  call    cs:__imp_RtlLeaveCriticalSection
0x1800309e6  mov     eax, esi
0x1800309e8  mov     rcx, [rsp+0E8h+var_48]
0x1800309f0  xor     rcx, rsp; StackCookie
0x1800309f3  call    __security_check_cookie
0x1800309f8  add     rsp, 0B0h
0x1800309ff  pop     r15
0x180030a01  pop     r14
0x180030a03  pop     r13
0x180030a05  pop     r12
0x180030a07  pop     rdi
0x180030a08  pop     rsi
0x180030a09  pop     rbx
0x180030a0a  retn
```
