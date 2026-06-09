# CSendReceive::RemoveConnection(void)

- ea: `0x1800b4630`
- end: `0x1800b47f0`
- name: `?RemoveConnection@CSendReceive@@UEAAXXZ`
- size: `448`
- prototype: `void __fastcall(CSendReceive *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x1800b4630`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800b46b5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800b46b5`

## string_xrefs

- `0x1800b4663`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b46bf`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4700`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4781`: `com\complus\dtc\dtc\cmhelper\cmhelper.cpp`
- `0x1800b4642`: `Entering CSendReceive::RemoveConnection, this=%p`
- `0x1800b4656`: `CSendReceive::RemoveConnection`

## pseudocode

```c
void __fastcall CSendReceive::RemoveConnection(CSendReceive *this)
{
  int v1; // esi
  char *v3; // rdi
  __int64 v4; // rcx
  void *v5; // rcx
  int v6; // [rsp+40h] [rbp-38h]

  v1 = 0;
  TraceStringInline(
    1,
    5,
    L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
    1926,
    L"CSendReceive::RemoveConnection",
    0,
    L"Entering CSendReceive::RemoveConnection, this=%p",
    this);
  v3 = (char *)this + 120;
  (**((void (__fastcall ***)(char *))this + 15))((char *)this + 120);
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    if ( *((_DWORD *)this + 44) == 2 )
    {
      v5 = (void *)*((_QWORD *)this + 14);
      *((_DWORD *)this + 44) = 3;
      ResetEvent(v5);
      v1 = 1;
      TraceStringInline(
        1,
        5,
        L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
        1940,
        L"CSendReceive::RemoveConnection",
        0,
        L"Set m_State to SR_DISCONNECTING, reset m_hConnectionStatus=0x%x, and fDisconnect=TRUE",
        *((_QWORD *)this + 14));
    }
    else
    {
      v6 = *((_DWORD *)this + 44);
      TraceStringInline(
        1,
        5,
        L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
        1944,
        L"CSendReceive::RemoveConnection",
        0,
        L"m_pIConnection=%p and m_State=0x%x",
        v4,
        v6);
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 120);
  if ( v1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
    (**(void (__fastcall ***)(char *))v3)((char *)this + 120);
    if ( *((_DWORD *)this + 44) == 4 )
    {
      if ( *((_QWORD *)this + 1) )
      {
        TraceStringInline(
          1,
          5,
          L"com\\complus\\dtc\\dtc\\cmhelper\\cmhelper.cpp",
          1958,
          L"CSendReceive::RemoveConnection",
          0,
          L"Disconnecting m_pIConnection=%p",
          *((_QWORD *)this + 1));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1));
        *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
        *((_QWORD *)this + 1) = 0;
      }
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 120);
  }
}

```

## disassembly

```asm
0x1800b4630  mov     r11, rsp
0x1800b4633  push    rbx
0x1800b4634  push    rsi
0x1800b4635  push    rdi
0x1800b4636  push    r13
0x1800b4638  push    r14
0x1800b463a  sub     rsp, 50h
0x1800b463e  mov     [r11-40h], rcx
0x1800b4642  lea     rax, aEnteringCsendr; "Entering CSendReceive::RemoveConnection"...
0x1800b4649  xor     esi, esi
0x1800b464b  mov     [r11-48h], rax
0x1800b464f  mov     rbx, rcx
0x1800b4652  mov     [r11-50h], rsi
0x1800b4656  lea     r13, aCsendreceiveRe; "CSendReceive::RemoveConnection"
0x1800b465d  mov     r9d, 786h
0x1800b4663  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b466a  mov     [r11-58h], r13
0x1800b466e  lea     r14d, [rsi+1]
0x1800b4672  mov     ecx, r14d
0x1800b4675  lea     edx, [rsi+5]
0x1800b4678  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b467d  lea     rdi, [rbx+78h]
0x1800b4681  mov     rax, [rdi]
0x1800b4684  mov     rcx, rdi
0x1800b4687  mov     rax, [rax]
0x1800b468a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b468f  mov     rcx, [rbx+8]
0x1800b4693  test    rcx, rcx
0x1800b4696  jz      loc_1800B4735
0x1800b469c  mov     eax, [rbx+0B0h]
0x1800b46a2  cmp     eax, 2
0x1800b46a5  jnz     short loc_1800B46FC
0x1800b46a7  mov     rcx, [rbx+70h]; hEvent
0x1800b46ab  mov     dword ptr [rbx+0B0h], 3
0x1800b46b5  call    cs:__imp_ResetEvent
0x1800b46bb  mov     rax, [rbx+70h]
0x1800b46bf  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b46c6  mov     [rsp+78h+var_40], rax
0x1800b46cb  lea     edx, [r14+4]
0x1800b46cf  lea     rax, aSetMStateToSrD; "Set m_State to SR_DISCONNECTING, reset "...
0x1800b46d6  mov     r9d, 794h
0x1800b46dc  mov     [rsp+78h+var_48], rax
0x1800b46e1  mov     ecx, r14d
0x1800b46e4  mov     [rsp+78h+var_50], 0
0x1800b46ed  mov     esi, r14d
0x1800b46f0  mov     [rsp+78h+var_58], r13
0x1800b46f5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b46fa  jmp     short loc_1800B4735
0x1800b46fc  mov     [rsp+78h+var_38], eax
0x1800b4700  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4707  mov     [rsp+78h+var_40], rcx
0x1800b470c  lea     rax, aMPiconnectionP; "m_pIConnection=%p and m_State=0x%x"
0x1800b4713  mov     [rsp+78h+var_48], rax
0x1800b4718  mov     r9d, 798h
0x1800b471e  mov     [rsp+78h+var_50], rsi
0x1800b4723  mov     edx, 5
0x1800b4728  mov     ecx, r14d
0x1800b472b  mov     [rsp+78h+var_58], r13
0x1800b4730  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b4735  mov     rax, [rdi]
0x1800b4738  mov     rcx, rdi
0x1800b473b  mov     rax, [rax+8]
0x1800b473f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4744  test    esi, esi
0x1800b4746  jz      loc_1800B47E4
0x1800b474c  mov     rcx, [rbx+8]
0x1800b4750  mov     rax, [rcx]
0x1800b4753  mov     rax, [rax+20h]
0x1800b4757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b475c  mov     rax, [rdi]
0x1800b475f  mov     rcx, rdi
0x1800b4762  mov     rax, [rax]
0x1800b4765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b476a  cmp     dword ptr [rbx+0B0h], 4
0x1800b4771  jnz     short loc_1800B47D5
0x1800b4773  mov     rax, [rbx+8]
0x1800b4777  test    rax, rax
0x1800b477a  jz      short loc_1800B47D5
0x1800b477c  mov     [rsp+78h+var_40], rax
0x1800b4781  lea     r8, aComComplusDtcD_109; "com\\complus\\dtc\\dtc\\cmhelper\\cmhel"...
0x1800b4788  lea     rax, aDisconnectingM; "Disconnecting m_pIConnection=%p"
0x1800b478f  mov     r9d, 7A6h
0x1800b4795  mov     [rsp+78h+var_48], rax
0x1800b479a  mov     edx, 5
0x1800b479f  mov     [rsp+78h+var_50], 0
0x1800b47a8  mov     ecx, r14d
0x1800b47ab  mov     [rsp+78h+var_58], r13
0x1800b47b0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800b47b5  mov     rcx, [rbx+8]
0x1800b47b9  mov     rax, [rcx]
0x1800b47bc  mov     rax, [rax+28h]
0x1800b47c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47c5  mov     rax, [rbx+8]
0x1800b47c9  mov     [rbx+10h], rax
0x1800b47cd  mov     qword ptr [rbx+8], 0
0x1800b47d5  mov     rax, [rdi]
0x1800b47d8  mov     rcx, rdi
0x1800b47db  mov     rax, [rax+8]
0x1800b47df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47e4  add     rsp, 50h
0x1800b47e8  pop     r14
0x1800b47ea  pop     r13
0x1800b47ec  pop     rdi
0x1800b47ed  pop     rsi
0x1800b47ee  pop     rbx
0x1800b47ef  retn
```
