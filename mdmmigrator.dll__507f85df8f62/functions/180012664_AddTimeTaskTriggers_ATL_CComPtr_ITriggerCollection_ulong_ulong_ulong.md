# AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)

- ea: `0x180012664`
- end: `0x180012a50`
- name: `?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z`
- size: `1004`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019abc`

## callees

- `0x1800022e0`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x180012664`
- `0x180012b58`
- `0x180012d2c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012721`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012721`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180012731`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180012731`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800127a0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800127a0`

## pseudocode

```c
__int64 __fastcall AddTimeTaskTriggers(_QWORD *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v6; // rsi
  signed int v7; // ebx
  BOOL v8; // eax
  struct _FILETIME v9; // rax
  unsigned int v10; // r8d
  signed int LastError; // eax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64); // rdi
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // r9d
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64); // rdi
  const struct std::nothrow_t *v18; // rdx
  bool v19; // sf
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64); // rdi
  const struct std::nothrow_t *v22; // rdx
  struct _FILETIME v24; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+58h] [rbp-A8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v32[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v33[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v34[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  SystemTime = 0;
  v30 = 0;
  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*a1 + 80LL))(*a1, 1, &v28);
  if ( v7 < 0 )
    goto LABEL_25;
  v7 = (**v28)(v28, &IID_ITimeTrigger, &v27);
  if ( v7 < 0 )
    goto LABEL_25;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  v8 = SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( (_DWORD)v4 )
  {
    if ( v8 )
    {
      v24 = FileTime;
      v9 = (struct _FILETIME)(600000000 * v4 + *(_QWORD *)&FileTime);
LABEL_8:
      v24 = v9;
      v7 = 0;
      FileTime = v9;
      if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
        goto LABEL_11;
    }
  }
  else if ( v8 )
  {
    v24 = FileTime;
    v9 = (struct _FILETIME)(*(_QWORD *)&FileTime + 600000000LL);
    goto LABEL_8;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  if ( v7 >= 0 )
  {
    v7 = CreateDelayTimeString(&SystemTime, v32, v10);
    if ( v7 >= 0 )
    {
      v12 = v27;
      v13 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 120LL);
      _bstr_t::_bstr_t((_bstr_t *)&v24, v32);
      v7 = v13(v12);
      _bstr_t::~_bstr_t((_bstr_t *)&v24, v14);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 80LL))(v27, &v26);
        if ( v7 >= 0 )
        {
          if ( (_DWORD)v6 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 96LL))(v26, 0xFFFFFFFFLL);
            if ( v7 < 0 )
              goto LABEL_25;
            v15 = v5 * v6;
            if ( (unsigned __int64)(v5 * v6) > 0xFFFFFFFF )
            {
              v7 = -2147024362;
              goto LABEL_25;
            }
            WORD5(v29) = v15 % 0x3C;
            WORD4(v29) = v15 / 0x3C % 0x18;
            WORD3(v29) = v15 / 0x3C / 0x18;
            LODWORD(v29) = 0;
            v7 = CreateScheduleTimeString(&v29, v33);
            if ( v7 < 0 )
              goto LABEL_25;
            v16 = v26;
            v17 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL);
            _bstr_t::_bstr_t((_bstr_t *)&v24, v33);
            v7 = v17(v16);
            _bstr_t::~_bstr_t((_bstr_t *)&v24, v18);
            v19 = v7 < 0;
          }
          else
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 96LL))(v26, 0);
            v19 = v7 < 0;
          }
          if ( !v19 )
          {
            WORD5(v30) = (unsigned int)v5 % 0x3C;
            WORD4(v30) = (unsigned int)v5 / 0x3C % 0x18;
            WORD3(v30) = (unsigned int)v5 / 0x3C / 0x18;
            LODWORD(v30) = 0;
            v7 = CreateScheduleTimeString(&v30, v34);
            if ( v7 >= 0 )
            {
              v20 = v26;
              v21 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 64LL);
              _bstr_t::_bstr_t((_bstr_t *)&v24, v34);
              v7 = v21(v20);
              _bstr_t::~_bstr_t((_bstr_t *)&v24, v22);
            }
          }
        }
      }
    }
  }
LABEL_25:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012664  mov     [rsp-8+arg_8], rbx
0x180012669  mov     [rsp-8+arg_10], rsi
0x18001266e  push    rbp
0x18001266f  push    rdi
0x180012670  push    r14
0x180012672  lea     rbp, [rsp-5C0h]
0x18001267a  sub     rsp, 6C0h
0x180012681  mov     rax, cs:__security_cookie
0x180012688  xor     rax, rsp
0x18001268b  mov     [rbp+5D0h+var_20], rax
0x180012692  mov     edi, r9d
0x180012695  mov     r14d, r8d
0x180012698  mov     esi, edx
0x18001269a  mov     [rsp+6D0h+var_690], 0
0x1800126a3  mov     [rsp+6D0h+var_698], 0
0x1800126ac  mov     [rsp+6D0h+var_6A0], 0
0x1800126b5  xorps   xmm0, xmm0
0x1800126b8  movups  xmmword ptr [rsp+6D0h+SystemTime.wYear], xmm0
0x1800126bd  xorps   xmm1, xmm1
0x1800126c0  movups  [rsp+6D0h+var_678], xmm1
0x1800126c5  movups  [rsp+6D0h+var_688], xmm0
0x1800126ca  mov     rcx, [rcx]
0x1800126cd  mov     rax, [rcx]
0x1800126d0  lea     r8, [rsp+6D0h+var_690]
0x1800126d5  mov     edx, 1
0x1800126da  mov     rax, [rax+50h]
0x1800126de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e3  mov     ebx, eax
0x1800126e5  test    eax, eax
0x1800126e7  js      loc_1800129EF
0x1800126ed  mov     rcx, [rsp+6D0h+var_690]
0x1800126f2  mov     rax, [rcx]
0x1800126f5  lea     r8, [rsp+6D0h+var_698]
0x1800126fa  lea     rdx, IID_ITimeTrigger
0x180012701  mov     rax, [rax]
0x180012704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012709  mov     ebx, eax
0x18001270b  test    eax, eax
0x18001270d  js      loc_1800129EF
0x180012713  mov     qword ptr [rsp+6D0h+FileTime.dwLowDateTime], 0
0x18001271c  lea     rcx, [rsp+6D0h+SystemTime]; lpSystemTime
0x180012721  call    cs:__imp_GetSystemTime
0x180012727  lea     rdx, [rsp+6D0h+FileTime]; lpFileTime
0x18001272c  lea     rcx, [rsp+6D0h+SystemTime]; lpSystemTime
0x180012731  call    cs:__imp_SystemTimeToFileTime
0x180012737  test    edi, edi
0x180012739  jnz     short loc_18001275C
0x18001273b  test    eax, eax
0x18001273d  jz      short loc_1800127AA
0x18001273f  mov     eax, [rsp+6D0h+FileTime.dwHighDateTime]
0x180012743  mov     dword ptr [rsp+6D0h+var_6B0+4], eax
0x180012747  mov     eax, [rsp+6D0h+FileTime.dwLowDateTime]
0x18001274b  mov     dword ptr [rsp+6D0h+var_6B0], eax
0x18001274f  mov     rax, [rsp+6D0h+var_6B0]
0x180012754  add     rax, 23C34600h
0x18001275a  jmp     short loc_18001277F
0x18001275c  test    eax, eax
0x18001275e  jz      short loc_1800127AA
0x180012760  mov     eax, [rsp+6D0h+FileTime.dwHighDateTime]
0x180012764  mov     dword ptr [rsp+6D0h+var_6B0+4], eax
0x180012768  mov     eax, [rsp+6D0h+FileTime.dwLowDateTime]
0x18001276c  mov     dword ptr [rsp+6D0h+var_6B0], eax
0x180012770  imul    rcx, rdi, 23C34600h
0x180012777  mov     rax, [rsp+6D0h+var_6B0]
0x18001277c  add     rax, rcx
0x18001277f  mov     [rsp+6D0h+var_6B0], rax
0x180012784  shr     rax, 20h
0x180012788  mov     [rsp+6D0h+FileTime.dwHighDateTime], eax
0x18001278c  mov     eax, dword ptr [rsp+6D0h+var_6B0]
0x180012790  xor     ebx, ebx
0x180012792  mov     [rsp+6D0h+FileTime.dwLowDateTime], eax
0x180012796  lea     rdx, [rsp+6D0h+SystemTime]; lpSystemTime
0x18001279b  lea     rcx, [rsp+6D0h+FileTime]; lpFileTime
0x1800127a0  call    cs:__imp_FileTimeToSystemTime
0x1800127a6  test    eax, eax
0x1800127a8  jnz     short loc_1800127BF
0x1800127aa  call    cs:__imp_GetLastError
0x1800127b0  test    eax, eax
0x1800127b2  mov     ebx, eax
0x1800127b4  jle     short loc_1800127BF
0x1800127b6  movzx   ebx, ax
0x1800127b9  or      ebx, 80070000h
0x1800127bf  test    ebx, ebx
0x1800127c1  js      loc_1800129EF
0x1800127c7  lea     rdx, [rbp+5D0h+var_650]; unsigned __int16 *
0x1800127cb  lea     rcx, [rsp+6D0h+SystemTime]; struct _SYSTEMTIME *
0x1800127d0  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x1800127d5  mov     ebx, eax
0x1800127d7  test    eax, eax
0x1800127d9  js      loc_1800129EF
0x1800127df  mov     rbx, [rsp+6D0h+var_698]
0x1800127e4  mov     rax, [rbx]
0x1800127e7  mov     rdi, [rax+78h]
0x1800127eb  lea     rdx, [rbp+5D0h+var_650]; unsigned __int16 *
0x1800127ef  lea     rcx, [rsp+6D0h+var_6B0]; this
0x1800127f4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800127f9  mov     rdx, [rax]
0x1800127fc  test    rdx, rdx
0x1800127ff  jz      short loc_180012804
0x180012801  mov     rdx, [rdx]
0x180012804  mov     rcx, rbx
0x180012807  mov     rax, rdi
0x18001280a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001280f  mov     ebx, eax
0x180012811  lea     rcx, [rsp+6D0h+var_6B0]; this
0x180012816  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001281b  test    ebx, ebx
0x18001281d  js      loc_1800129EF
0x180012823  mov     rcx, [rsp+6D0h+var_698]
0x180012828  mov     rax, [rcx]
0x18001282b  lea     rdx, [rsp+6D0h+var_6A0]
0x180012830  mov     rax, [rax+50h]
0x180012834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012839  mov     ebx, eax
0x18001283b  test    eax, eax
0x18001283d  js      loc_1800129EF
0x180012843  mov     rcx, [rsp+6D0h+var_6A0]
0x180012848  test    esi, esi
0x18001284a  jz      loc_180012933
0x180012850  mov     rax, [rcx]
0x180012853  or      edx, 0FFFFFFFFh
0x180012856  mov     rax, [rax+60h]
0x18001285a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001285f  mov     ebx, eax
0x180012861  test    eax, eax
0x180012863  js      loc_1800129EF
0x180012869  mov     r9, rsi
0x18001286c  imul    r9, r14
0x180012870  mov     eax, 0FFFFFFFFh
0x180012875  cmp     r9, rax
0x180012878  ja      loc_180012929
0x18001287e  mov     eax, 88888889h
0x180012883  mul     r9d
0x180012886  mov     r8d, edx
0x180012889  shr     r8d, 5
0x18001288d  movzx   eax, r8w
0x180012891  imul    ecx, eax, 3Ch ; '<'
0x180012894  sub     r9w, cx
0x180012898  mov     word ptr [rsp+6D0h+var_688+0Ah], r9w
0x18001289e  mov     eax, 0AAAAAAABh
0x1800128a3  mul     r8d
0x1800128a6  shr     edx, 4
0x1800128a9  movzx   eax, dx
0x1800128ac  add     ax, ax
0x1800128af  lea     ecx, [rax+rdx]
0x1800128b2  shl     cx, 3
0x1800128b6  sub     r8w, cx
0x1800128ba  mov     word ptr [rsp+6D0h+var_688+8], r8w
0x1800128c0  mov     word ptr [rsp+6D0h+var_688+6], dx
0x1800128c5  xor     eax, eax
0x1800128c7  mov     dword ptr [rsp+6D0h+var_688], eax
0x1800128cb  lea     rdx, [rbp+5D0h+var_440]
0x1800128d2  lea     rcx, [rsp+6D0h+var_688]
0x1800128d7  call    CreateScheduleTimeString
0x1800128dc  mov     ebx, eax
0x1800128de  test    eax, eax
0x1800128e0  js      loc_1800129EF
0x1800128e6  mov     rbx, [rsp+6D0h+var_6A0]
0x1800128eb  mov     rax, [rbx]
0x1800128ee  mov     rdi, [rax+50h]
0x1800128f2  lea     rdx, [rbp+5D0h+var_440]; unsigned __int16 *
0x1800128f9  lea     rcx, [rsp+6D0h+var_6B0]; this
0x1800128fe  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180012903  mov     rdx, [rax]
0x180012906  test    rdx, rdx
0x180012909  jz      short loc_18001290E
0x18001290b  mov     rdx, [rdx]
0x18001290e  mov     rcx, rbx
0x180012911  mov     rax, rdi
0x180012914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012919  mov     ebx, eax
0x18001291b  lea     rcx, [rsp+6D0h+var_6B0]; this
0x180012920  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180012925  test    ebx, ebx
0x180012927  jmp     short loc_180012945
0x180012929  mov     ebx, 80070216h
0x18001292e  jmp     loc_1800129EF
0x180012933  mov     r8, [rcx]
0x180012936  xor     edx, edx
0x180012938  mov     rax, [r8+60h]
0x18001293c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012941  mov     ebx, eax
0x180012943  test    eax, eax
0x180012945  js      loc_1800129EF
0x18001294b  mov     eax, 88888889h
0x180012950  mul     r14d
0x180012953  mov     r9d, edx
0x180012956  shr     r9d, 5
0x18001295a  movzx   ecx, r9w
0x18001295e  imul    r8d, ecx, 3Ch ; '<'
0x180012962  sub     r14w, r8w
0x180012966  mov     word ptr [rsp+6D0h+var_678+0Ah], r14w
0x18001296c  mov     eax, 0AAAAAAABh
0x180012971  mul     r9d
0x180012974  shr     edx, 4
0x180012977  movzx   eax, dx
0x18001297a  add     ax, ax
0x18001297d  lea     ecx, [rax+rdx]
0x180012980  shl     cx, 3
0x180012984  sub     r9w, cx
0x180012988  mov     word ptr [rsp+6D0h+var_678+8], r9w
0x18001298e  mov     word ptr [rsp+6D0h+var_678+6], dx
0x180012993  xor     eax, eax
0x180012995  mov     dword ptr [rsp+6D0h+var_678], eax
0x180012999  lea     rdx, [rbp+5D0h+var_230]
0x1800129a0  lea     rcx, [rsp+6D0h+var_678]
0x1800129a5  call    CreateScheduleTimeString
0x1800129aa  mov     ebx, eax
0x1800129ac  test    eax, eax
0x1800129ae  js      short loc_1800129EF
0x1800129b0  mov     rbx, [rsp+6D0h+var_6A0]
0x1800129b5  mov     rax, [rbx]
0x1800129b8  mov     rdi, [rax+40h]
0x1800129bc  lea     rdx, [rbp+5D0h+var_230]; unsigned __int16 *
0x1800129c3  lea     rcx, [rsp+6D0h+var_6B0]; this
0x1800129c8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800129cd  mov     rdx, [rax]
0x1800129d0  test    rdx, rdx
0x1800129d3  jz      short loc_1800129D8
0x1800129d5  mov     rdx, [rdx]
0x1800129d8  mov     rcx, rbx
0x1800129db  mov     rax, rdi
0x1800129de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129e3  mov     ebx, eax
0x1800129e5  lea     rcx, [rsp+6D0h+var_6B0]; this
0x1800129ea  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800129ef  mov     rcx, [rsp+6D0h+var_6A0]
0x1800129f4  test    rcx, rcx
0x1800129f7  jz      short loc_180012A05
0x1800129f9  mov     rax, [rcx]
0x1800129fc  mov     rax, [rax+10h]
0x180012a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a05  mov     rcx, [rsp+6D0h+var_698]
0x180012a0a  test    rcx, rcx
0x180012a0d  jz      short loc_180012A1C
0x180012a0f  mov     rax, [rcx]
0x180012a12  mov     rax, [rax+10h]
0x180012a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a1b  nop
0x180012a1c  lea     rcx, [rsp+6D0h+var_690]
0x180012a21  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180012a26  nop
0x180012a27  mov     eax, ebx
0x180012a29  mov     rcx, [rbp+5D0h+var_20]
0x180012a30  xor     rcx, rsp; StackCookie
0x180012a33  call    __security_check_cookie
0x180012a38  lea     r11, [rsp+6D0h+var_10]
0x180012a40  mov     rbx, [r11+28h]
0x180012a44  mov     rsi, [r11+30h]
0x180012a48  mov     rsp, r11
0x180012a4b  pop     r14
0x180012a4d  pop     rdi
0x180012a4e  pop     rbp
0x180012a4f  retn
```
