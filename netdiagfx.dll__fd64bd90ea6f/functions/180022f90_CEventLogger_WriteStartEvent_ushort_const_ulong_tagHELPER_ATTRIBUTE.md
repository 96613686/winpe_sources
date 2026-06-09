# CEventLogger::WriteStartEvent(ushort const *,ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x180022f90`
- end: `0x1800230ea`
- name: `?WriteStartEvent@CEventLogger@@UEAAJPEBGKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `346`
- prototype: `int(CEventLogger *__hidden this, const unsigned __int16 *, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056bc`
- `0x180006d58`
- `0x18001edc0`
- `0x180022150`
- `0x180022f90`
- `0x1800264ec`
- `0x18002c840`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180022fd2`
- `msvcrt!wcsnlen` at `0x180022fd2`
- `ADVAPI32!EventWrite` at `0x1800230ab`
- `ADVAPI32!EventWrite` at `0x1800230ab`
- `ADVAPI32!EventEnabled` at `0x18002308b`
- `ADVAPI32!EventEnabled` at `0x18002308b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CEventLogger::WriteStartEvent(
        CEventLogger *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct tagHELPER_ATTRIBUTE *a4)
{
  size_t v6; // rax
  __int64 v7; // rbx
  unsigned int i; // r8d
  struct tagHELPER_ATTRIBUTE *v9; // rdx
  _QWORD *v10; // rax
  int v11; // ecx
  unsigned int v12; // ebx
  signed int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-50h] BYREF
  __int64 v16; // [rsp+28h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-40h] BYREF
  unsigned int *v18; // [rsp+40h] [rbp-30h]
  __int64 v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+50h] [rbp-20h]
  int v21; // [rsp+58h] [rbp-18h]
  int v22; // [rsp+5Ch] [rbp-14h]
  unsigned int v23; // [rsp+A0h] [rbp+30h] BYREF

  v23 = a3;
  if ( !a2 || !a4 && a3 )
    return 2147942487LL;
  v6 = wcsnlen(a2, 0x100u);
  UserData.Ptr = (ULONGLONG)a2;
  UserData.Size = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v6 + 2);
  UserData.Reserved = 0;
  v18 = &v23;
  v19 = 4;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v15,
    (__int64)&qword_180033960);
  v7 = 0;
  for ( i = v23; (unsigned int)v7 < i; v7 = (unsigned int)(v7 + 1) )
  {
    v9 = &a4[v7];
    if ( v9 )
    {
      v10 = (_QWORD *)AttributeConverter::ToString(&v16, v9);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v15, *v10, *(unsigned int *)(*v10 - 16LL));
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
      i = v23;
    }
  }
  v11 = 2 * *(_DWORD *)(v15 - 16) + 2;
  v20 = v15;
  v21 = v11;
  v22 = 0;
  v12 = 0;
  if ( EventEnabled(NETDIAG_EVT_GUID_Context, &NDFStartEvtDesc) )
  {
    v13 = EventWrite(NETDIAG_EVT_GUID_Context, &NDFStartEvtDesc, 3u, &UserData);
    v12 = v13;
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
  return v12;
}

```

## disassembly

```asm
0x180022f90  mov     [rsp-18h+arg_10], r8d
0x180022f95  push    rbp
0x180022f96  push    rbx
0x180022f97  push    rdi
0x180022f98  mov     rbp, rsp
0x180022f9b  sub     rsp, 70h
0x180022f9f  mov     rax, cs:__security_cookie
0x180022fa6  xor     rax, rsp
0x180022fa9  mov     [rbp+var_10], rax
0x180022fad  mov     rdi, r9
0x180022fb0  mov     rbx, rdx
0x180022fb3  test    rdx, rdx
0x180022fb6  jz      loc_1800230D1
0x180022fbc  test    r9, r9
0x180022fbf  jnz     short loc_180022FCA
0x180022fc1  test    r8d, r8d
0x180022fc4  jnz     loc_1800230D1
0x180022fca  mov     edx, 100h; MaxCount
0x180022fcf  mov     rcx, rbx; Source
0x180022fd2  call    cs:__imp_wcsnlen
0x180022fd8  lea     rcx, ds:2[rax*2]
0x180022fe0  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180022fe5  mov     [rbp+UserData.Ptr], rbx
0x180022fe9  mov     [rbp+UserData.Size], eax
0x180022fec  mov     dword ptr [rbp+UserData.0Ch], 0
0x180022ff3  lea     rax, [rbp+arg_10]
0x180022ff7  mov     [rbp+var_30], rax
0x180022ffb  mov     [rbp+var_28], 4
0x180023003  lea     rdx, qword_180033960
0x18002300a  lea     rcx, [rbp+var_50]
0x18002300e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180023013  nop
0x180023014  xor     ebx, ebx
0x180023016  mov     r8d, [rbp+arg_10]
0x18002301a  test    r8d, r8d
0x18002301d  jz      short loc_18002305F
0x18002301f  lea     rdx, [rbx+rbx*8]
0x180023023  shl     rdx, 4
0x180023027  add     rdx, rdi
0x18002302a  jz      short loc_180023058
0x18002302c  lea     rcx, [rbp+var_48]
0x180023030  call    ?ToString@AttributeConverter@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBUtagHELPER_ATTRIBUTE@@@Z; AttributeConverter::ToString(tagHELPER_ATTRIBUTE const *)
0x180023035  nop
0x180023036  mov     rdx, [rax]
0x180023039  mov     r8d, [rdx-10h]
0x18002303d  lea     rcx, [rbp+var_50]
0x180023041  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180023046  nop
0x180023047  mov     rcx, [rbp+var_48]
0x18002304b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002304f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023054  mov     r8d, [rbp+arg_10]
0x180023058  inc     ebx
0x18002305a  cmp     ebx, r8d
0x18002305d  jb      short loc_18002301F
0x18002305f  mov     rax, [rbp+var_50]
0x180023063  mov     ecx, [rax-10h]
0x180023066  lea     ecx, ds:2[rcx*2]
0x18002306d  mov     [rbp+var_20], rax
0x180023071  mov     [rbp+var_18], ecx
0x180023074  mov     [rbp+var_14], 0
0x18002307b  xor     ebx, ebx
0x18002307d  lea     rdx, NDFStartEvtDesc; EventDescriptor
0x180023084  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x18002308b  call    cs:__imp_EventEnabled
0x180023091  test    al, al
0x180023093  jz      short loc_1800230C0
0x180023095  lea     r9, [rbp+UserData]; UserData
0x180023099  lea     r8d, [rbx+3]; UserDataCount
0x18002309d  lea     rdx, NDFStartEvtDesc; EventDescriptor
0x1800230a4  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x1800230ab  call    cs:__imp_EventWrite
0x1800230b1  mov     ebx, eax
0x1800230b3  test    eax, eax
0x1800230b5  jle     short loc_1800230C0
0x1800230b7  movzx   ebx, ax
0x1800230ba  or      ebx, 80070000h
0x1800230c0  mov     rcx, [rbp+var_50]
0x1800230c4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800230c8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800230cd  mov     eax, ebx
0x1800230cf  jmp     short loc_1800230D6
0x1800230d1  mov     eax, 80070057h
0x1800230d6  mov     rcx, [rbp+var_10]
0x1800230da  xor     rcx, rsp; StackCookie
0x1800230dd  call    __security_check_cookie
0x1800230e2  add     rsp, 70h
0x1800230e6  pop     rdi
0x1800230e7  pop     rbx
0x1800230e8  pop     rbp
0x1800230e9  retn
```
