# SNI_Conn::InitObject(SNI_Conn * *,int)

- ea: `0x100413898`
- end: `0x100413c80`
- name: `?InitObject@SNI_Conn@@SAKPEAPEAV1@H@Z`
- size: `1000`
- prototype: `unsigned int __fastcall(struct SNI_Conn **, int)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x100417890`
- `0x100437530`

## callees

- `0x100411c50`
- `0x100413898`
- `0x100413d10`
- `0x1004158c0`
- `0x10043857c`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x100413aa7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100413aa7`
- `RPCRT4!UuidCreate` at `0x100413ac5`
- `RPCRT4!UuidCreate` at `0x100413ac5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SNI_Conn::InitObject(struct SNI_Conn **a1)
{
  unsigned int v2; // ebx
  SNI_Conn *v3; // rax
  SNI_Conn *v4; // rax
  SNI_Conn *v5; // rsi
  unsigned int v6; // edi
  wchar_t *v7; // r8
  __int64 v8; // rdx
  SNI_Sec *v9; // rax
  SNI_Sec *v10; // rax
  __int64 v11; // rax
  _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF
  SNI_Conn *v15; // [rsp+78h] [rbp+20h]

  v14 = -1;
  v2 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7730[0] )
    bidScopeEnterW(&v14, off_1005E7730[0], a1);
  *a1 = 0;
  v3 = (SNI_Conn *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 336);
  v15 = v3;
  if ( !v3 || (v4 = SNI_Conn::SNI_Conn(v3), (v5 = v4) == 0) )
  {
    v6 = 14;
    if ( (bidGblFlags & 2) != 0 && off_1005E44E8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 459776, off_1005E44E8[0], 9);
    }
    SNISetLastError(9, 14, 50100);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E44F0[0] )
      goto LABEL_40;
    v7 = off_1005E44F0[0];
    v8 = 461824;
    goto LABEL_39;
  }
  v6 = CCriticalSectionNT_SNI::Initialize((struct CCriticalSectionNT_SNI **)v4 + 5);
  if ( v6 )
  {
    SNI_Conn::Release(v5, 0);
    if ( (bidGblFlags & 2) != 0 && off_1005E44F8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 474112, off_1005E44F8[0], 9);
    }
    SNISetLastError(9, v6, 50100);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E4500[0] )
      goto LABEL_40;
    v7 = off_1005E4500[0];
    v8 = 476160;
LABEL_39:
    bidTraceW(0, v8, v7, v6);
LABEL_40:
    v2 = v6;
    goto LABEL_41;
  }
  v9 = (SNI_Sec *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 56);
  v15 = v9;
  if ( v9 )
    v10 = SNI_Sec::SNI_Sec(v9);
  else
    v10 = 0;
  *((_QWORD *)v5 + 30) = v10;
  if ( !v10 )
  {
    SNI_Conn::Release(v5, 0);
    v6 = 14;
    if ( (bidGblFlags & 2) != 0 && off_1005E4508[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 487424, off_1005E4508[0], 9);
    }
    SNISetLastError(9, 14, 50100);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E4510[0] )
      goto LABEL_40;
    v7 = off_1005E4510[0];
    v8 = 489472;
    goto LABEL_39;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((_FILETIME *)v5 + 28) = SystemTimeAsFileTime;
  v6 = UuidCreate((UUID *)((char *)v5 + 4));
  if ( v6 )
  {
    SNI_Conn::Release(v5, 0);
    if ( (bidGblFlags & 2) != 0 && off_1005E4518[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 510976, off_1005E4518[0], 9);
    }
    SNISetLastError(9, v6, 50100);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E4520[0] )
      goto LABEL_40;
    v7 = off_1005E4520[0];
    v8 = 513024;
    goto LABEL_39;
  }
  *((_QWORD *)v5 + 39) = *((_QWORD *)SNI_MemRegions::s_pClientMemRegions + 1);
  v11 = ((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&SNI_Conn::iSniConnIndex, 1u) + 1) & 0x7FF;
  *((_DWORD *)v5 + 9) = v11;
  (&SNI_Conn::rgSniConn)[v11] = (struct SNI_Conn * near *)v5;
  *a1 = v5;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4528[0] )
    bidTraceW(0, 529408, off_1005E4528[0], 0);
LABEL_41:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v14);
  return v2;
}

```

## disassembly

```asm
0x100413898  mov     r11, rsp
0x10041389b  push    rsi
0x10041389c  push    rdi
0x10041389d  push    r14
0x10041389f  sub     rsp, 40h
0x1004138a3  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x1004138ab  mov     [r11+10h], rbx
0x1004138af  mov     r14, rcx
0x1004138b2  or      qword ptr [r11+18h], 0FFFFFFFFFFFFFFFFh
0x1004138b7  mov     eax, cs:_bidGblFlags
0x1004138bd  mov     ecx, 20004h
0x1004138c2  and     eax, ecx
0x1004138c4  xor     ebx, ebx
0x1004138c6  cmp     eax, ecx
0x1004138c8  jnz     short loc_1004138EC
0x1004138ca  mov     rax, cs:off_1005E7730; "<SNI_Conn::InitObject|API|SNI> ppConn: "...
0x1004138d1  test    rax, rax
0x1004138d4  jz      short loc_1004138EC
0x1004138d6  mov     r9d, edx
0x1004138d9  mov     r8, r14
0x1004138dc  mov     rdx, cs:off_1005E7730; "<SNI_Conn::InitObject|API|SNI> ppConn: "...
0x1004138e3  lea     rcx, [r11+18h]
0x1004138e7  call    _bidScopeEnterW
0x1004138ec  mov     [r14], rbx
0x1004138ef  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1004138f6  mov     rax, [rcx]
0x1004138f9  mov     edx, 150h
0x1004138fe  mov     rax, [rax+58h]
0x100413902  call    cs:__guard_dispatch_icall_fptr
0x100413908  mov     [rsp+58h+arg_18], rax
0x10041390d  test    rax, rax
0x100413910  jz      loc_100413BDD
0x100413916  mov     rcx, rax; this
0x100413919  call    ??0SNI_Conn@@AEAA@XZ; SNI_Conn::SNI_Conn(void)
0x10041391e  mov     rsi, rax
0x100413921  test    rax, rax
0x100413924  jz      loc_100413BDD
0x10041392a  lea     rcx, [rax+28h]; struct CCriticalSectionNT_SNI **
0x10041392e  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x100413933  mov     edi, eax
0x100413935  test    eax, eax
0x100413937  jz      loc_1004139CE
0x10041393d  xor     edx, edx
0x10041393f  mov     rcx, rsi
0x100413942  call    ?Release@SNI_Conn@@QEAAJW4SNI_REF@@@Z; SNI_Conn::Release(SNI_REF)
0x100413947  mov     esi, 0C3B4h
0x10041394c  test    byte ptr cs:_bidGblFlags, 2
0x100413953  jz      short loc_100413989
0x100413955  mov     rax, cs:off_1005E44F8; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x10041395c  test    rax, rax
0x10041395f  jz      short loc_100413989
0x100413961  mov     ecx, esi; unsigned int
0x100413963  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100413968  mov     [rsp+58h+var_30], edi
0x10041396c  mov     [rsp+58h+var_38], eax
0x100413970  mov     r9d, 9
0x100413976  mov     r8, cs:off_1005E44F8; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x10041397d  mov     edx, 73C00h
0x100413982  xor     ecx, ecx
0x100413984  call    _bidTraceW
0x100413989  mov     r8d, esi
0x10041398c  mov     edx, edi
0x10041398e  mov     ecx, 9
0x100413993  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100413998  mov     eax, cs:_bidGblFlags
0x10041399e  mov     ecx, 20002h
0x1004139a3  and     eax, ecx
0x1004139a5  cmp     eax, ecx
0x1004139a7  jnz     loc_100413C64
0x1004139ad  mov     rax, cs:off_1005E4500; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x1004139b4  test    rax, rax
0x1004139b7  jz      loc_100413C64
0x1004139bd  mov     r8, cs:off_1005E4500; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x1004139c4  mov     edx, 74400h
0x1004139c9  jmp     loc_100413C5A
0x1004139ce  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1004139d5  mov     rax, [rcx]
0x1004139d8  mov     edx, 38h ; '8'
0x1004139dd  mov     rax, [rax+58h]
0x1004139e1  call    cs:__guard_dispatch_icall_fptr
0x1004139e7  mov     [rsp+58h+arg_18], rax
0x1004139ec  test    rax, rax
0x1004139ef  jz      short loc_1004139FB
0x1004139f1  mov     rcx, rax; this
0x1004139f4  call    ??0SNI_Sec@@AEAA@XZ; SNI_Sec::SNI_Sec(void)
0x1004139f9  jmp     short loc_1004139FE
0x1004139fb  mov     rax, rbx
0x1004139fe  mov     [rsi+0F0h], rax
0x100413a05  test    rax, rax
0x100413a08  jnz     loc_100413AA2
0x100413a0e  xor     edx, edx
0x100413a10  mov     rcx, rsi
0x100413a13  call    ?Release@SNI_Conn@@QEAAJW4SNI_REF@@@Z; SNI_Conn::Release(SNI_REF)
0x100413a18  mov     esi, 0C3B4h
0x100413a1d  mov     edi, 0Eh
0x100413a22  test    byte ptr cs:_bidGblFlags, 2
0x100413a29  jz      short loc_100413A5D
0x100413a2b  mov     rax, cs:off_1005E4508; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x100413a32  test    rax, rax
0x100413a35  jz      short loc_100413A5D
0x100413a37  mov     ecx, esi; unsigned int
0x100413a39  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100413a3e  mov     [rsp+58h+var_30], edi
0x100413a42  mov     [rsp+58h+var_38], eax
0x100413a46  lea     r9d, [rdi-5]
0x100413a4a  mov     r8, cs:off_1005E4508; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x100413a51  mov     edx, 77000h
0x100413a56  xor     ecx, ecx
0x100413a58  call    _bidTraceW
0x100413a5d  mov     r8d, esi
0x100413a60  mov     edx, edi
0x100413a62  mov     ecx, 9
0x100413a67  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100413a6c  mov     eax, cs:_bidGblFlags
0x100413a72  mov     ecx, 20002h
0x100413a77  and     eax, ecx
0x100413a79  cmp     eax, ecx
0x100413a7b  jnz     loc_100413C64
0x100413a81  mov     rax, cs:off_1005E4510; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413a88  test    rax, rax
0x100413a8b  jz      loc_100413C64
0x100413a91  mov     r8, cs:off_1005E4510; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413a98  mov     edx, 77800h
0x100413a9d  jmp     loc_100413C5A
0x100413aa2  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100413aa7  call    cs:__imp_GetSystemTimeAsFileTime
0x100413aad  mov     eax, [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x100413ab1  mov     [rsi+0E0h], eax
0x100413ab7  mov     eax, [rsp+58h+SystemTimeAsFileTime.dwHighDateTime]
0x100413abb  mov     [rsi+0E4h], eax
0x100413ac1  lea     rcx, [rsi+4]; Uuid
0x100413ac5  call    cs:__imp_UuidCreate
0x100413acb  mov     edi, eax
0x100413acd  test    eax, eax
0x100413acf  jz      loc_100413B66
0x100413ad5  xor     edx, edx
0x100413ad7  mov     rcx, rsi
0x100413ada  call    ?Release@SNI_Conn@@QEAAJW4SNI_REF@@@Z; SNI_Conn::Release(SNI_REF)
0x100413adf  mov     esi, 0C3B4h
0x100413ae4  test    byte ptr cs:_bidGblFlags, 2
0x100413aeb  jz      short loc_100413B21
0x100413aed  mov     rax, cs:off_1005E4518; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x100413af4  test    rax, rax
0x100413af7  jz      short loc_100413B21
0x100413af9  mov     ecx, esi; unsigned int
0x100413afb  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100413b00  mov     [rsp+58h+var_30], edi
0x100413b04  mov     [rsp+58h+var_38], eax
0x100413b08  mov     r9d, 9
0x100413b0e  mov     r8, cs:off_1005E4518; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x100413b15  mov     edx, 7CC00h
0x100413b1a  xor     ecx, ecx
0x100413b1c  call    _bidTraceW
0x100413b21  mov     r8d, esi
0x100413b24  mov     edx, edi
0x100413b26  mov     ecx, 9
0x100413b2b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100413b30  mov     eax, cs:_bidGblFlags
0x100413b36  mov     ecx, 20002h
0x100413b3b  and     eax, ecx
0x100413b3d  cmp     eax, ecx
0x100413b3f  jnz     loc_100413C64
0x100413b45  mov     rax, cs:off_1005E4520; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413b4c  test    rax, rax
0x100413b4f  jz      loc_100413C64
0x100413b55  mov     r8, cs:off_1005E4520; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413b5c  mov     edx, 7D400h
0x100413b61  jmp     loc_100413C5A
0x100413b66  mov     rax, cs:?s_pClientMemRegions@SNI_MemRegions@@2PEAV1@EA; SNI_MemRegions * SNI_MemRegions::s_pClientMemRegions
0x100413b6d  mov     rcx, [rax+8]
0x100413b71  mov     [rsi+138h], rcx
0x100413b78  mov     eax, 1
0x100413b7d  lock xadd cs:?iSniConnIndex@SNI_Conn@@0KA, eax; ulong SNI_Conn::iSniConnIndex
0x100413b85  inc     eax
0x100413b87  and     eax, 7FFh
0x100413b8c  mov     [rsi+24h], eax
0x100413b8f  lea     rcx, ?rgSniConn@SNI_Conn@@0PAPEAV1@A; SNI_Conn * near * SNI_Conn::rgSniConn
0x100413b96  mov     [rcx+rax*8], rsi
0x100413b9a  mov     [r14], rsi
0x100413b9d  mov     eax, cs:_bidGblFlags
0x100413ba3  mov     ecx, 20002h
0x100413ba8  and     eax, ecx
0x100413baa  cmp     eax, ecx
0x100413bac  jnz     loc_100413C66
0x100413bb2  mov     rax, cs:off_1005E4528; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413bb9  test    rax, rax
0x100413bbc  jz      loc_100413C66
0x100413bc2  xor     r9d, r9d
0x100413bc5  mov     r8, cs:off_1005E4528; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413bcc  mov     edx, 81400h
0x100413bd1  xor     ecx, ecx
0x100413bd3  call    _bidTraceW
0x100413bd8  jmp     loc_100413C66
0x100413bdd  mov     esi, 0C3B4h
0x100413be2  mov     edi, 0Eh
0x100413be7  test    byte ptr cs:_bidGblFlags, 2
0x100413bee  jz      short loc_100413C22
0x100413bf0  mov     rax, cs:off_1005E44E8; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x100413bf7  test    rax, rax
0x100413bfa  jz      short loc_100413C22
0x100413bfc  mov     ecx, esi; unsigned int
0x100413bfe  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100413c03  mov     [rsp+58h+var_30], edi
0x100413c07  mov     [rsp+58h+var_38], eax
0x100413c0b  lea     r9d, [rdi-5]
0x100413c0f  mov     r8, cs:off_1005E44E8; "<SNI_Conn::InitObject|ERR|SNI> Provider"...
0x100413c16  mov     edx, 70400h
0x100413c1b  xor     ecx, ecx
0x100413c1d  call    _bidTraceW
0x100413c22  mov     r8d, esi
0x100413c25  mov     edx, edi
0x100413c27  mov     ecx, 9
0x100413c2c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100413c31  mov     eax, cs:_bidGblFlags
0x100413c37  mov     ecx, 20002h
0x100413c3c  and     eax, ecx
0x100413c3e  cmp     eax, ecx
0x100413c40  jnz     short loc_100413C64
0x100413c42  mov     rax, cs:off_1005E44F0; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413c49  test    rax, rax
0x100413c4c  jz      short loc_100413C64
0x100413c4e  mov     r8, cs:off_1005E44F0; "<SNI_Conn::InitObject|RET|SNI> %d{WINER"...
0x100413c55  mov     edx, 70C00h
0x100413c5a  mov     r9d, edi
0x100413c5d  xor     ecx, ecx
0x100413c5f  call    _bidTraceW
0x100413c64  mov     ebx, edi
0x100413c66  lea     rcx, [rsp+58h+arg_10]; this
0x100413c6b  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100413c70  mov     eax, ebx
0x100413c72  mov     rbx, [rsp+58h+arg_8]
0x100413c77  add     rsp, 40h
0x100413c7b  pop     r14
0x100413c7d  pop     rdi
0x100413c7e  pop     rsi
0x100413c7f  retn
```
