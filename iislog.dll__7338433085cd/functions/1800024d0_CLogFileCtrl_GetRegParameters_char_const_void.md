# CLogFileCtrl::GetRegParameters(char const *,void *)

- ea: `0x1800024d0`
- end: `0x18000272d`
- name: `?GetRegParameters@CLogFileCtrl@@MEAAKPEBDPEAX@Z`
- size: `605`
- prototype: `unsigned int __fastcall(CLogFileCtrl *__hidden this, const char *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004810`

## callees

- `0x180002410`
- `0x1800024d0`
- `0x180003030`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000269b`
- `msvcrt!strcpy_s` at `0x18000269b`
- `KERNEL32!SetLastError` at `0x180002570`
- `KERNEL32!SetLastError` at `0x180002570`
- `KERNEL32!GetLastError` at `0x180002576`
- `KERNEL32!GetLastError` at `0x180002576`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x1800026d7`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x1800026d7`

## string_xrefs

- `0x18000268a`: `%systemroot%\system32\LogFiles`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::GetRegParameters(CLogFileCtrl *this, const char *a2, void *a3)
{
  int v5; // eax
  unsigned int v6; // r9d
  DWORD v7; // ecx
  DWORD LastError; // ebx
  unsigned int v10; // r9d
  int v11; // eax
  int v12; // eax
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  char Destination[272]; // [rsp+70h] [rbp-90h] BYREF
  CHAR Dst[272]; // [rsp+180h] [rbp+80h] BYREF

  v17 = 0;
  v14 = 0;
  v13 = 0;
  v16 = *((_QWORD *)this + 8);
  v18[0] = 261;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const char *, __int64, int, int *))(*(_QWORD *)v16 + 272LL))(
         v16,
         0,
         byte_180013080,
         1,
         5000,
         &v17);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v15 = 4;
    if ( !(unsigned int)MB::GetData((MB *)&v16, a2, 0xFA3u, v6, 1u, &v13, &v15, 1u) || (v11 = v13, v13 > 4) )
    {
      v11 = 1;
      v13 = 1;
    }
    *((_DWORD *)this + 27) = v11;
    *((_DWORD *)this + 26) = -1;
    if ( !v11 )
    {
      v15 = 4;
      if ( (unsigned int)MB::GetData((MB *)&v16, a2, 0xFA4u, v10, 1u, &v14, &v15, 1u) )
      {
        v12 = v14;
        if ( v14 < 0x20000 )
        {
          v12 = 0x20000;
          v14 = 0x20000;
        }
        *((_DWORD *)this + 26) = v12;
      }
    }
    if ( !(unsigned int)MB::GetData((MB *)&v16, a2, 0xFA1u, v10, 4u, Destination, v18, 1u) )
      strcpy_s(Destination, 0x105u, "%systemroot%\\system32\\LogFiles");
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 288LL))(v16);
      v17 = 0;
    }
    ExpandEnvironmentStringsA(Destination, Dst, 0x105u);
    CLogFileCtrl::SetLogFileDirectory(this, Dst);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 288LL))(v16);
    return 0;
  }
  else
  {
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v7 = (unsigned __int16)v5;
    SetLastError(v7);
    LastError = GetLastError();
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 288LL))(v16);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800024d0  mov     [rsp-8+arg_10], rbx
0x1800024d5  push    rbp
0x1800024d6  push    rdi
0x1800024d7  push    r14
0x1800024d9  lea     rbp, [rsp-1A0h]
0x1800024e1  sub     rsp, 2A0h
0x1800024e8  mov     rax, cs:__security_cookie
0x1800024ef  xor     rax, rsp
0x1800024f2  mov     [rbp+1B0h+var_20], rax
0x1800024f9  mov     rdi, rdx
0x1800024fc  mov     [rsp+2B0h+var_258], 0
0x180002504  lea     rdx, [rsp+2B0h+var_258]
0x180002509  mov     [rsp+2B0h+var_26C], 0
0x180002511  mov     [rsp+2B0h+var_288], rdx
0x180002516  lea     r8, byte_180013080
0x18000251d  mov     rbx, rcx
0x180002520  mov     [rsp+2B0h+var_270], 0
0x180002528  mov     rcx, [rcx+40h]
0x18000252c  mov     r14d, 1
0x180002532  mov     [rsp+2B0h+var_260], rcx
0x180002537  mov     r9d, r14d
0x18000253a  xor     edx, edx
0x18000253c  mov     [rsp+2B0h+var_250], 105h
0x180002544  mov     [rsp+2B0h+var_290], 1388h
0x18000254c  mov     rax, [rcx]
0x18000254f  mov     rax, [rax+110h]
0x180002556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255b  mov     ecx, eax
0x18000255d  test    eax, eax
0x18000255f  jns     short loc_1800025A4
0x180002561  and     eax, 1FFF0000h
0x180002566  cmp     eax, 70000h
0x18000256b  jnz     short loc_180002570
0x18000256d  movzx   ecx, cx; dwErrCode
0x180002570  call    cs:__imp_SetLastError
0x180002576  call    cs:__imp_GetLastError
0x18000257c  mov     edx, [rsp+2B0h+var_258]
0x180002580  mov     ebx, eax
0x180002582  test    edx, edx
0x180002584  jz      short loc_18000259D
0x180002586  mov     r8, [rsp+2B0h+var_260]
0x18000258b  mov     rcx, [r8]
0x18000258e  mov     rax, [rcx+120h]
0x180002595  mov     rcx, r8
0x180002598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259d  mov     eax, ebx
0x18000259f  jmp     loc_18000270A
0x1800025a4  mov     [rsp+2B0h+var_278], r14d; unsigned int
0x1800025a9  lea     rax, [rsp+2B0h+var_268]
0x1800025ae  mov     [rsp+2B0h+var_280], rax; unsigned int *
0x1800025b3  lea     rcx, [rsp+2B0h+var_260]; this
0x1800025b8  lea     rax, [rsp+2B0h+var_270]
0x1800025bd  mov     [rsp+2B0h+var_268], 4
0x1800025c5  mov     [rsp+2B0h+var_288], rax; void *
0x1800025ca  mov     r8d, 0FA3h; unsigned int
0x1800025d0  mov     rdx, rdi; char *
0x1800025d3  mov     [rsp+2B0h+var_290], r14d; unsigned int
0x1800025d8  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x1800025dd  test    eax, eax
0x1800025df  jz      short loc_1800025EA
0x1800025e1  mov     eax, [rsp+2B0h+var_270]
0x1800025e5  cmp     eax, 4
0x1800025e8  jbe     short loc_1800025F1
0x1800025ea  mov     eax, r14d
0x1800025ed  mov     [rsp+2B0h+var_270], eax
0x1800025f1  mov     [rbx+6Ch], eax
0x1800025f4  mov     dword ptr [rbx+68h], 0FFFFFFFFh
0x1800025fb  test    eax, eax
0x1800025fd  jnz     short loc_180002652
0x1800025ff  mov     [rsp+2B0h+var_278], r14d; unsigned int
0x180002604  lea     rax, [rsp+2B0h+var_268]
0x180002609  mov     [rsp+2B0h+var_280], rax; unsigned int *
0x18000260e  lea     rcx, [rsp+2B0h+var_260]; this
0x180002613  lea     rax, [rsp+2B0h+var_26C]
0x180002618  mov     [rsp+2B0h+var_268], 4
0x180002620  mov     [rsp+2B0h+var_288], rax; void *
0x180002625  mov     r8d, 0FA4h; unsigned int
0x18000262b  mov     rdx, rdi; char *
0x18000262e  mov     [rsp+2B0h+var_290], r14d; unsigned int
0x180002633  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180002638  test    eax, eax
0x18000263a  jz      short loc_180002652
0x18000263c  mov     eax, [rsp+2B0h+var_26C]
0x180002640  mov     ecx, 20000h
0x180002645  cmp     eax, ecx
0x180002647  jnb     short loc_18000264F
0x180002649  mov     eax, ecx
0x18000264b  mov     [rsp+2B0h+var_26C], ecx
0x18000264f  mov     [rbx+68h], eax
0x180002652  mov     [rsp+2B0h+var_278], r14d; unsigned int
0x180002657  lea     rax, [rsp+2B0h+var_250]
0x18000265c  mov     [rsp+2B0h+var_280], rax; unsigned int *
0x180002661  lea     rcx, [rsp+2B0h+var_260]; this
0x180002666  lea     rax, [rsp+2B0h+Destination]
0x18000266b  mov     r8d, 0FA1h; unsigned int
0x180002671  mov     [rsp+2B0h+var_288], rax; void *
0x180002676  mov     rdx, rdi; char *
0x180002679  mov     [rsp+2B0h+var_290], 4; unsigned int
0x180002681  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180002686  test    eax, eax
0x180002688  jnz     short loc_1800026A1
0x18000268a  lea     r8, Source; "%systemroot%\\system32\\LogFiles"
0x180002691  mov     edx, 105h; SizeInBytes
0x180002696  lea     rcx, [rsp+2B0h+Destination]; Destination
0x18000269b  call    cs:__imp_strcpy_s
0x1800026a1  mov     edx, [rsp+2B0h+var_258]
0x1800026a5  test    edx, edx
0x1800026a7  jz      short loc_1800026C5
0x1800026a9  mov     rcx, [rsp+2B0h+var_260]
0x1800026ae  mov     rax, [rcx]
0x1800026b1  mov     rax, [rax+120h]
0x1800026b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026bd  mov     [rsp+2B0h+var_258], 0
0x1800026c5  mov     r8d, 105h; nSize
0x1800026cb  lea     rdx, [rbp+1B0h+Dst]; lpDst
0x1800026d2  lea     rcx, [rsp+2B0h+Destination]; lpSrc
0x1800026d7  call    cs:__imp_ExpandEnvironmentStringsA
0x1800026dd  lea     rdx, [rbp+1B0h+Dst]; char *
0x1800026e4  mov     rcx, rbx; this
0x1800026e7  call    ?SetLogFileDirectory@CLogFileCtrl@@AEAAXPEBD@Z; CLogFileCtrl::SetLogFileDirectory(char const *)
0x1800026ec  mov     edx, [rsp+2B0h+var_258]
0x1800026f0  test    edx, edx
0x1800026f2  jz      short loc_180002708
0x1800026f4  mov     rcx, [rsp+2B0h+var_260]
0x1800026f9  mov     rax, [rcx]
0x1800026fc  mov     rax, [rax+120h]
0x180002703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002708  xor     eax, eax
0x18000270a  mov     rcx, [rbp+1B0h+var_20]
0x180002711  xor     rcx, rsp; StackCookie
0x180002714  call    __security_check_cookie
0x180002719  mov     rbx, [rsp+2B0h+arg_10]
0x180002721  add     rsp, 2A0h
0x180002728  pop     r14
0x18000272a  pop     rdi
0x18000272b  pop     rbp
0x18000272c  retn
```
