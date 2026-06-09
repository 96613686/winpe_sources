# CTmProxyCore::GetKtmRmTmHandle(int,void * *)

- ea: `0x1800104c0`
- end: `0x18001077e`
- name: `?GetKtmRmTmHandle@CTmProxyCore@@QEAAJHPEAPEAX@Z`
- size: `702`
- prototype: `__int64 __fastcall(CTmProxyCore *__hidden this, int, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002847c`
- `0x180042ca0`
- `0x180042f90`

## callees

- `0x180003cf0`
- `0x1800104c0`
- `0x180011ac0`
- `0x18007f82c`
- `0x18007f8a0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106df`
- `ktmw32!OpenTransactionManagerById` at `0x1800106a0`
- `ktmw32!OpenTransactionManagerById` at `0x1800106a0`

## string_xrefs

- `0x1800106ca`: `CTmProxyCore::GetKtmRmTmHandle - error from OpenTransactionManagerById`
- `0x18001071d`: `com\complus\dtc\dtc\msdtcprx\src\dtcprx.cpp`
- `0x180010599`: `com\complus\dtc\dtc\msdtcprx\src\dtcprx.cpp`

## pseudocode

```c
__int64 __fastcall CTmProxyCore::GetKtmRmTmHandle(CTmProxyCore *this, int a2, void **a3)
{
  CIConnSink *v3; // rdi
  unsigned int v6; // ebx
  struct CSendReceive *Instance; // rax
  int v8; // ecx
  char *v9; // rdx
  unsigned int v10; // r9d
  __int64 v11; // r8
  int v12; // eax
  HANDLE v13; // rax
  signed int LastError; // eax
  int v16; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+80h] [rbp+18h] BYREF
  LPGUID TransactionManagerId; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  *a3 = (void *)-1LL;
  v16 = 0;
  TransactionManagerId = 0;
  v17 = 0;
  if ( *((_QWORD *)this + 4) )
  {
    *a3 = (void *)*((_QWORD *)this + 4);
LABEL_3:
    v6 = 0;
    goto LABEL_35;
  }
  if ( !a2 )
    goto LABEL_3;
  Instance = CSendReceive::CreateInstance();
  v3 = Instance;
  if ( !Instance )
  {
    v8 = -2147024882;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - can't allocate CSendReceive";
    v10 = 982;
LABEL_33:
    v6 = v8;
    goto LABEL_34;
  }
  if ( !(*(unsigned int (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance + 32LL))(Instance) )
  {
    CIConnSink::DeleteObject(v3);
    v8 = -2147024882;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - can't initialize CSendReceive";
    v3 = 0;
    v10 = 991;
    goto LABEL_33;
  }
  (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 160LL))(v3);
  v11 = *((_QWORD *)this + 440);
  if ( !v11 )
  {
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprx.cpp",
      999,
      L"CTmProxyCore::GetKtmRmTmHandle",
      0,
      L"CTmProxyCore::GetKtmRmTmHandle - m_pINameObjKtmRm is NULL, check KTMRM CIDs");
    v6 = -2147168217;
    goto LABEL_35;
  }
  v12 = (*(__int64 (__fastcall **)(CIConnSink *, _QWORD, __int64, __int64, int))(*(_QWORD *)v3 + 248LL))(
          v3,
          *((_QWORD *)this + 443),
          v11,
          1,
          4099);
  v6 = v12;
  if ( v12 < 0 )
  {
    v10 = 1012;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - error from CSendReceive::Connect";
LABEL_13:
    v8 = v12;
LABEL_34:
    TraceFile(v8, v9, "com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprx.cpp", v10);
    goto LABEL_35;
  }
  v12 = (*(__int64 (__fastcall **)(CIConnSink *, __int64, _QWORD, _QWORD, int *, LPGUID *, _DWORD, int *))(*(_QWORD *)v3 + 96LL))(
          v3,
          1073741856,
          0,
          0,
          &v16,
          &TransactionManagerId,
          0,
          &v17);
  v6 = v12;
  if ( v12 )
  {
    v10 = 1027;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - error from CSendReceive::SendReceive";
    goto LABEL_13;
  }
  if ( v16 != 1073741857 )
  {
    if ( v16 != 9 )
    {
      v10 = 1055;
      v9 = "CTmProxyCore::GetKtmRmTmHandle - unexpected return MTAG for KtmRm";
      goto LABEL_32;
    }
    v6 = -2147168228;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - connection to KtmRm went down";
    v10 = 1049;
LABEL_25:
    v8 = v6;
    goto LABEL_34;
  }
  if ( v17 != 16 )
  {
    v10 = 1036;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - bad result message length";
LABEL_32:
    v8 = -2147418113;
    goto LABEL_33;
  }
  if ( !TransactionManagerId )
  {
    v10 = 1042;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - null result message";
    goto LABEL_32;
  }
  v13 = OpenTransactionManagerById(TransactionManagerId, 0x20u, 0);
  if ( v13 == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v10 = 1064;
    v9 = "CTmProxyCore::GetKtmRmTmHandle - error from OpenTransactionManagerById";
    goto LABEL_25;
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 4, (signed __int64)v13, 0) )
    CloseHandle(v13);
  *a3 = (void *)*((_QWORD *)this + 4);
LABEL_35:
  if ( TransactionManagerId )
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 120LL))(v3);
  if ( v3 )
  {
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 272LL))(v3);
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v3 + 168LL))(v3);
  }
  return v6;
}

```

## disassembly

```asm
0x1800104c0  mov     rax, rsp
0x1800104c3  mov     [rax+10h], rbx
0x1800104c7  push    rsi
0x1800104c8  push    rdi
0x1800104c9  push    r14
0x1800104cb  sub     rsp, 50h
0x1800104cf  xor     edi, edi
0x1800104d1  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x1800104d8  mov     [rax+8], edi
0x1800104db  mov     r14, r8
0x1800104de  mov     [rax+20h], rdi
0x1800104e2  mov     rsi, rcx
0x1800104e5  mov     [rax+18h], edi
0x1800104e8  mov     rax, [rcx+20h]
0x1800104ec  test    rax, rax
0x1800104ef  jz      short loc_1800104FF
0x1800104f1  mov     rax, [rcx+20h]
0x1800104f5  mov     [r8], rax
0x1800104f8  xor     ebx, ebx
0x1800104fa  jmp     loc_180010729
0x1800104ff  test    edx, edx
0x180010501  jz      short loc_1800104F8
0x180010503  call    ?CreateInstance@CSendReceive@@SAPEAV1@XZ; CSendReceive::CreateInstance(void)
0x180010508  mov     rdi, rax
0x18001050b  test    rax, rax
0x18001050e  jnz     short loc_180010527
0x180010510  mov     ecx, 8007000Eh
0x180010515  lea     rdx, aCtmproxycoreGe; "CTmProxyCore::GetKtmRmTmHandle - can't "...
0x18001051c  mov     r9d, 3D6h
0x180010522  jmp     loc_18001071B
0x180010527  mov     rax, [rax]
0x18001052a  mov     rcx, rdi
0x18001052d  mov     rax, [rax+20h]
0x180010531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010536  mov     rcx, rdi; this
0x180010539  test    eax, eax
0x18001053b  jnz     short loc_18001055B
0x18001053d  call    ?DeleteObject@CIConnSink@@UEAAXXZ; CIConnSink::DeleteObject(void)
0x180010542  mov     ecx, 8007000Eh
0x180010547  lea     rdx, aCtmproxycoreGe_3; "CTmProxyCore::GetKtmRmTmHandle - can't "...
0x18001054e  xor     edi, edi
0x180010550  mov     r9d, 3DFh
0x180010556  jmp     loc_18001071B
0x18001055b  mov     rax, [rdi]
0x18001055e  mov     rax, [rax+0A0h]
0x180010565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001056a  mov     r8, [rsi+0DC0h]
0x180010571  test    r8, r8
0x180010574  jnz     short loc_1800105B7
0x180010576  mov     edx, 1
0x18001057b  lea     rax, aCtmproxycoreGe_0; "CTmProxyCore::GetKtmRmTmHandle - m_pINa"...
0x180010582  mov     [rsp+68h+var_38], rax
0x180010587  mov     r9d, 3E7h
0x18001058d  mov     [rsp+68h+var_40], r8
0x180010592  lea     rax, aCtmproxycoreGe_2; "CTmProxyCore::GetKtmRmTmHandle"
0x180010599  lea     r8, aComComplusDtcD_28; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800105a0  mov     [rsp+68h+var_48], rax
0x1800105a5  lea     ecx, [rdx+0Eh]
0x1800105a8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800105ad  mov     ebx, 8004D027h
0x1800105b2  jmp     loc_180010729
0x1800105b7  mov     rax, [rdi]
0x1800105ba  mov     r9d, 1
0x1800105c0  mov     rdx, [rsi+0DD8h]
0x1800105c7  mov     rcx, rdi
0x1800105ca  mov     dword ptr [rsp+68h+var_48], 1003h
0x1800105d2  mov     rax, [rax+0F8h]
0x1800105d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105de  mov     ebx, eax
0x1800105e0  test    eax, eax
0x1800105e2  jns     short loc_1800105F8
0x1800105e4  mov     r9d, 3F4h
0x1800105ea  lea     rdx, aCtmproxycoreGe_6; "CTmProxyCore::GetKtmRmTmHandle - error "...
0x1800105f1  mov     ecx, eax
0x1800105f3  jmp     loc_18001071D
0x1800105f8  mov     rax, [rdi]
0x1800105fb  lea     rcx, [rsp+68h+arg_10]
0x180010603  mov     [rsp+68h+var_30], rcx
0x180010608  xor     r9d, r9d
0x18001060b  lea     rcx, [rsp+68h+TransactionManagerId]
0x180010613  mov     dword ptr [rsp+68h+var_38], 0
0x18001061b  mov     [rsp+68h+var_40], rcx
0x180010620  xor     r8d, r8d
0x180010623  mov     rax, [rax+60h]
0x180010627  lea     rcx, [rsp+68h+arg_0]
0x18001062c  mov     [rsp+68h+var_48], rcx
0x180010631  mov     edx, 40000020h
0x180010636  mov     rcx, rdi
0x180010639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063e  mov     ebx, eax
0x180010640  test    eax, eax
0x180010642  jz      short loc_180010653
0x180010644  mov     r9d, 403h
0x18001064a  lea     rdx, aCtmproxycoreGe_9; "CTmProxyCore::GetKtmRmTmHandle - error "...
0x180010651  jmp     short loc_1800105F1
0x180010653  cmp     [rsp+68h+arg_0], 40000021h
0x18001065b  jnz     loc_1800106EE
0x180010661  cmp     [rsp+68h+arg_10], 10h
0x180010669  jz      short loc_18001067D
0x18001066b  mov     r9d, 40Ch
0x180010671  lea     rdx, aCtmproxycoreGe_8; "CTmProxyCore::GetKtmRmTmHandle - bad re"...
0x180010678  jmp     loc_180010716
0x18001067d  mov     rcx, [rsp+68h+TransactionManagerId]; TransactionManagerId
0x180010685  test    rcx, rcx
0x180010688  jnz     short loc_180010699
0x18001068a  mov     r9d, 412h
0x180010690  lea     rdx, aCtmproxycoreGe_7; "CTmProxyCore::GetKtmRmTmHandle - null r"...
0x180010697  jmp     short loc_180010716
0x180010699  xor     r8d, r8d; OpenOptions
0x18001069c  lea     edx, [r8+20h]; DesiredAccess
0x1800106a0  call    cs:__imp_OpenTransactionManagerById
0x1800106a6  mov     rcx, rax; hObject
0x1800106a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800106ad  jnz     short loc_1800106D5
0x1800106af  call    cs:__imp_GetLastError
0x1800106b5  mov     ebx, eax
0x1800106b7  test    eax, eax
0x1800106b9  jle     short loc_1800106C4
0x1800106bb  movzx   ebx, ax
0x1800106be  or      ebx, 80070000h
0x1800106c4  mov     r9d, 428h
0x1800106ca  lea     rdx, aCtmproxycoreGe_5; "CTmProxyCore::GetKtmRmTmHandle - error "...
0x1800106d1  mov     ecx, ebx
0x1800106d3  jmp     short loc_18001071D
0x1800106d5  xor     eax, eax
0x1800106d7  lock cmpxchg [rsi+20h], rcx
0x1800106dd  jz      short loc_1800106E5
0x1800106df  call    cs:__imp_CloseHandle
0x1800106e5  mov     rax, [rsi+20h]
0x1800106e9  mov     [r14], rax
0x1800106ec  jmp     short loc_180010729
0x1800106ee  cmp     [rsp+68h+arg_0], 9
0x1800106f3  jnz     short loc_180010709
0x1800106f5  mov     ebx, 8004D01Ch
0x1800106fa  lea     rdx, aCtmproxycoreGe_1; "CTmProxyCore::GetKtmRmTmHandle - connec"...
0x180010701  mov     r9d, 419h
0x180010707  jmp     short loc_1800106D1
0x180010709  mov     r9d, 41Fh; unsigned int
0x18001070f  lea     rdx, aCtmproxycoreGe_4; "CTmProxyCore::GetKtmRmTmHandle - unexpe"...
0x180010716  mov     ecx, 8000FFFFh; int
0x18001071b  mov     ebx, ecx
0x18001071d  lea     r8, aComComplusDtcD_13; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180010724  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010729  mov     rdx, [rsp+68h+TransactionManagerId]
0x180010731  test    rdx, rdx
0x180010734  jz      short loc_180010745
0x180010736  mov     rax, [rdi]
0x180010739  mov     rcx, rdi
0x18001073c  mov     rax, [rax+78h]
0x180010740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010745  test    rdi, rdi
0x180010748  jz      short loc_18001076E
0x18001074a  mov     rax, [rdi]
0x18001074d  mov     rcx, rdi
0x180010750  mov     rax, [rax+110h]
0x180010757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001075c  mov     rax, [rdi]
0x18001075f  mov     rcx, rdi
0x180010762  mov     rax, [rax+0A8h]
0x180010769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001076e  mov     eax, ebx
0x180010770  mov     rbx, [rsp+68h+arg_8]
0x180010775  add     rsp, 50h
0x180010779  pop     r14
0x18001077b  pop     rdi
0x18001077c  pop     rsi
0x18001077d  retn
```
