# AddTimeTaskTriggers(ATL::CComPtr<ITriggerCollection> &,ulong,ulong,ulong)

- ea: `0x18001d484`
- end: `0x18001d8ee`
- name: `?AddTimeTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@KKK@Z`
- size: `1130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021d40`
- `0x180038420`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x18001ce6c`
- `0x18001d484`
- `0x18001d9dc`
- `0x18001dbb0`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001d546`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001d546`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001d5c5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001d5c5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001d556`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001d556`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d634`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d75a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d8b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d634`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d75a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d8b0`

## pseudocode

```c
__int64 __fastcall AddTimeTaskTriggers(__int64 *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // rcx
  __int64 v5; // r15
  __int64 v6; // r14
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rax
  signed int v9; // ebx
  BOOL v10; // eax
  struct _FILETIME v11; // rax
  unsigned int v12; // r8d
  signed int LastError; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, BSTR); // rsi
  BSTR *v16; // rbx
  BSTR v17; // rax
  unsigned int v18; // r9d
  __int64 *v19; // rdi
  __int64 (__fastcall *v20)(__int64 *, BSTR); // rsi
  BSTR *v21; // rbx
  BSTR v22; // rax
  bool v23; // sf
  __int64 *v25; // rdi
  __int64 v26; // rsi
  BSTR *v27; // rbx
  BSTR v28; // rax
  struct _FILETIME v29; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-D8h] BYREF
  __int64 *v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+58h] [rbp-A8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR psz[264]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v38[264]; // [rsp+290h] [rbp+190h] BYREF
  OLECHAR v39[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v4 = *a1;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  SystemTime = 0;
  v5 = a3;
  v6 = a2;
  v7 = a4;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 80LL);
  v35 = 0;
  v34 = 0;
  v9 = v8(v4, 1, &v33);
  if ( v9 < 0 )
    goto LABEL_23;
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v33)(v33, &IID_ITimeTrigger, &v32);
  if ( v9 < 0 )
    goto LABEL_23;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  v10 = SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( (_DWORD)v7 )
  {
    if ( !v10 )
      goto LABEL_9;
    v29 = FileTime;
    v11 = (struct _FILETIME)(600000000 * v7 + *(_QWORD *)&FileTime);
  }
  else
  {
    if ( !v10 )
      goto LABEL_9;
    v29 = FileTime;
    v11 = (struct _FILETIME)(*(_QWORD *)&FileTime + 600000000LL);
  }
  v29 = v11;
  v9 = 0;
  FileTime = v11;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
LABEL_9:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v9 >= 0 )
  {
    v9 = CreateDelayTimeString(&SystemTime, psz, v12);
    if ( v9 >= 0 )
    {
      v14 = v32;
      v15 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v32 + 120LL);
      v16 = (BSTR *)operator new(0x18u);
      v16[1] = 0;
      *((_DWORD *)v16 + 4) = 1;
      v17 = SysAllocString(psz);
      *v16 = v17;
      if ( !v17 )
        goto LABEL_35;
      v29 = (struct _FILETIME)v16;
      v9 = v15(v14, v17);
      _bstr_t::~_bstr_t((_bstr_t *)&v29);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v32 + 80LL))(v32, &v31);
        if ( v9 >= 0 )
        {
          if ( (_DWORD)v6 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v31 + 96))(v31, 0xFFFFFFFFLL);
            if ( v9 < 0 )
              goto LABEL_23;
            v18 = v5 * v6;
            if ( (unsigned __int64)(v5 * v6) > 0xFFFFFFFF )
            {
              v9 = -2147024362;
              goto LABEL_23;
            }
            WORD3(v34) = v18 / 0x3C / 0x18;
            WORD5(v34) = v18 % 0x3C;
            LODWORD(v34) = 0;
            WORD4(v34) = v18 / 0x3C % 0x18;
            v9 = CreateScheduleTimeString(&v34, v38);
            if ( v9 < 0 )
              goto LABEL_23;
            v19 = v31;
            v20 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v31 + 80);
            v21 = (BSTR *)operator new(0x18u);
            v21[1] = 0;
            *((_DWORD *)v21 + 4) = 1;
            v22 = SysAllocString(v38);
            *v21 = v22;
            if ( !v22 )
              goto LABEL_35;
            v29 = (struct _FILETIME)v21;
            v9 = v20(v19, v22);
            _bstr_t::~_bstr_t((_bstr_t *)&v29);
            v23 = v9 < 0;
          }
          else
          {
            v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v31 + 96))(v31, 0);
            v23 = v9 < 0;
          }
          if ( !v23 )
          {
            WORD3(v35) = (unsigned int)v5 / 0x3C / 0x18;
            WORD5(v35) = (unsigned int)v5 % 0x3C;
            WORD4(v35) = (unsigned int)v5 / 0x3C % 0x18;
            LODWORD(v35) = 0;
            v9 = CreateScheduleTimeString(&v35, v39);
            if ( v9 >= 0 )
            {
              v25 = v31;
              v26 = *v31;
              v27 = (BSTR *)operator new(0x18u);
              v27[1] = 0;
              *((_DWORD *)v27 + 4) = 1;
              v28 = SysAllocString(v39);
              *v27 = v28;
              if ( v28 )
              {
                v29 = (struct _FILETIME)v27;
                v9 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v26 + 64))(v25, v28);
                _bstr_t::~_bstr_t((_bstr_t *)&v29);
                goto LABEL_23;
              }
LABEL_35:
              _com_issue_error(-2147024882);
            }
          }
        }
      }
    }
  }
LABEL_23:
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d484  mov     [rsp-8+arg_8], rbx
0x18001d489  mov     [rsp-8+arg_10], rsi
0x18001d48e  push    rbp
0x18001d48f  push    rdi
0x18001d490  push    r13
0x18001d492  push    r14
0x18001d494  push    r15
0x18001d496  lea     rbp, [rsp-5C0h]
0x18001d49e  sub     rsp, 6C0h
0x18001d4a5  mov     rax, cs:__security_cookie
0x18001d4ac  xor     rax, rsp
0x18001d4af  mov     [rbp+5E0h+var_30], rax
0x18001d4b6  mov     rcx, [rcx]
0x18001d4b9  xorps   xmm0, xmm0
0x18001d4bc  mov     [rsp+6E0h+var_6A0], 0
0x18001d4c5  xorps   xmm1, xmm1
0x18001d4c8  mov     [rsp+6E0h+var_6A8], 0
0x18001d4d1  mov     [rsp+6E0h+var_6B0], 0
0x18001d4da  movups  xmmword ptr [rsp+6E0h+SystemTime.wYear], xmm0
0x18001d4df  mov     rax, [rcx]
0x18001d4e2  mov     r15d, r8d
0x18001d4e5  lea     r8, [rsp+6E0h+var_6A0]
0x18001d4ea  mov     r14d, edx
0x18001d4ed  mov     edx, 1
0x18001d4f2  mov     edi, r9d
0x18001d4f5  mov     rax, [rax+50h]
0x18001d4f9  movups  [rsp+6E0h+var_688], xmm1
0x18001d4fe  movups  [rsp+6E0h+var_698], xmm0
0x18001d503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d508  mov     ebx, eax
0x18001d50a  test    eax, eax
0x18001d50c  js      loc_18001D797
0x18001d512  mov     rcx, [rsp+6E0h+var_6A0]
0x18001d517  lea     r8, [rsp+6E0h+var_6A8]
0x18001d51c  lea     rdx, IID_ITimeTrigger
0x18001d523  mov     rax, [rcx]
0x18001d526  mov     rax, [rax]
0x18001d529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d52e  mov     ebx, eax
0x18001d530  test    eax, eax
0x18001d532  js      loc_18001D797
0x18001d538  lea     rcx, [rsp+6E0h+SystemTime]; lpSystemTime
0x18001d53d  mov     qword ptr [rsp+6E0h+FileTime.dwLowDateTime], 0
0x18001d546  call    cs:__imp_GetSystemTime
0x18001d54c  lea     rdx, [rsp+6E0h+FileTime]; lpFileTime
0x18001d551  lea     rcx, [rsp+6E0h+SystemTime]; lpSystemTime
0x18001d556  call    cs:__imp_SystemTimeToFileTime
0x18001d55c  test    edi, edi
0x18001d55e  jnz     short loc_18001D581
0x18001d560  test    eax, eax
0x18001d562  jz      short loc_18001D5CF
0x18001d564  mov     eax, [rsp+6E0h+FileTime.dwHighDateTime]
0x18001d568  mov     dword ptr [rsp+6E0h+var_6C0+4], eax
0x18001d56c  mov     eax, [rsp+6E0h+FileTime.dwLowDateTime]
0x18001d570  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x18001d574  mov     rax, [rsp+6E0h+var_6C0]
0x18001d579  add     rax, 23C34600h
0x18001d57f  jmp     short loc_18001D5A4
0x18001d581  test    eax, eax
0x18001d583  jz      short loc_18001D5CF
0x18001d585  mov     eax, [rsp+6E0h+FileTime.dwHighDateTime]
0x18001d589  mov     dword ptr [rsp+6E0h+var_6C0+4], eax
0x18001d58d  mov     eax, [rsp+6E0h+FileTime.dwLowDateTime]
0x18001d591  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x18001d595  mov     rax, [rsp+6E0h+var_6C0]
0x18001d59a  imul    rcx, rdi, 23C34600h
0x18001d5a1  add     rax, rcx
0x18001d5a4  mov     [rsp+6E0h+var_6C0], rax
0x18001d5a9  lea     rdx, [rsp+6E0h+SystemTime]; lpSystemTime
0x18001d5ae  shr     rax, 20h
0x18001d5b2  lea     rcx, [rsp+6E0h+FileTime]; lpFileTime
0x18001d5b7  mov     [rsp+6E0h+FileTime.dwHighDateTime], eax
0x18001d5bb  xor     ebx, ebx
0x18001d5bd  mov     eax, dword ptr [rsp+6E0h+var_6C0]
0x18001d5c1  mov     [rsp+6E0h+FileTime.dwLowDateTime], eax
0x18001d5c5  call    cs:__imp_FileTimeToSystemTime
0x18001d5cb  test    eax, eax
0x18001d5cd  jnz     short loc_18001D5E4
0x18001d5cf  call    cs:__imp_GetLastError
0x18001d5d5  mov     ebx, eax
0x18001d5d7  test    eax, eax
0x18001d5d9  jle     short loc_18001D5E4
0x18001d5db  movzx   ebx, ax
0x18001d5de  or      ebx, 80070000h
0x18001d5e4  test    ebx, ebx
0x18001d5e6  js      loc_18001D797
0x18001d5ec  lea     rdx, [rbp+5E0h+psz]; unsigned __int16 *
0x18001d5f0  lea     rcx, [rsp+6E0h+SystemTime]; struct _SYSTEMTIME *
0x18001d5f5  call    ?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z; CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)
0x18001d5fa  mov     ebx, eax
0x18001d5fc  test    eax, eax
0x18001d5fe  js      loc_18001D797
0x18001d604  mov     rdi, [rsp+6E0h+var_6A8]
0x18001d609  mov     r13d, 18h
0x18001d60f  mov     ecx, r13d; Size
0x18001d612  mov     rax, [rdi]
0x18001d615  mov     rsi, [rax+78h]
0x18001d619  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d61e  lea     rcx, [rbp+5E0h+psz]; psz
0x18001d622  mov     rbx, rax
0x18001d625  mov     qword ptr [rax+8], 0
0x18001d62d  mov     dword ptr [rax+10h], 1
0x18001d634  call    cs:__imp_SysAllocString
0x18001d63a  mov     [rbx], rax
0x18001d63d  test    rax, rax
0x18001d640  jz      loc_18001D8E3
0x18001d646  mov     rdx, rax
0x18001d649  mov     [rsp+6E0h+var_6C0], rbx
0x18001d64e  mov     rax, rsi
0x18001d651  mov     rcx, rdi
0x18001d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d659  lea     rcx, [rsp+6E0h+var_6C0]; this
0x18001d65e  mov     ebx, eax
0x18001d660  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001d665  test    ebx, ebx
0x18001d667  js      loc_18001D797
0x18001d66d  mov     rcx, [rsp+6E0h+var_6A8]
0x18001d672  lea     rdx, [rsp+6E0h+var_6B0]
0x18001d677  mov     rax, [rcx]
0x18001d67a  mov     rax, [rax+50h]
0x18001d67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d683  mov     ebx, eax
0x18001d685  test    eax, eax
0x18001d687  js      loc_18001D797
0x18001d68d  mov     rcx, [rsp+6E0h+var_6B0]
0x18001d692  test    r14d, r14d
0x18001d695  jz      loc_18001D806
0x18001d69b  mov     rax, [rcx]
0x18001d69e  or      edx, 0FFFFFFFFh
0x18001d6a1  mov     rax, [rax+60h]
0x18001d6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6aa  mov     ebx, eax
0x18001d6ac  test    eax, eax
0x18001d6ae  js      loc_18001D797
0x18001d6b4  mov     r9, r14
0x18001d6b7  mov     eax, 0FFFFFFFFh
0x18001d6bc  imul    r9, r15
0x18001d6c0  cmp     r9, rax
0x18001d6c3  ja      loc_18001D792
0x18001d6c9  mov     eax, 88888889h
0x18001d6ce  mul     r9d
0x18001d6d1  mov     r8d, edx
0x18001d6d4  shr     r8d, 5
0x18001d6d8  movzx   eax, r8w
0x18001d6dc  imul    ecx, eax, 3Ch ; '<'
0x18001d6df  mov     eax, 0AAAAAAABh
0x18001d6e4  mul     r8d
0x18001d6e7  sub     r9w, cx
0x18001d6eb  shr     edx, 4
0x18001d6ee  movzx   eax, dx
0x18001d6f1  mov     word ptr [rsp+6E0h+var_698+6], dx
0x18001d6f6  add     ax, ax
0x18001d6f9  mov     word ptr [rsp+6E0h+var_698+0Ah], r9w
0x18001d6ff  lea     ecx, [rax+rdx]
0x18001d702  xor     eax, eax
0x18001d704  shl     cx, 3
0x18001d708  lea     rdx, [rbp+5E0h+var_450]
0x18001d70f  sub     r8w, cx
0x18001d713  mov     dword ptr [rsp+6E0h+var_698], eax
0x18001d717  lea     rcx, [rsp+6E0h+var_698]
0x18001d71c  mov     word ptr [rsp+6E0h+var_698+8], r8w
0x18001d722  call    CreateScheduleTimeString
0x18001d727  mov     ebx, eax
0x18001d729  test    eax, eax
0x18001d72b  js      short loc_18001D797
0x18001d72d  mov     rdi, [rsp+6E0h+var_6B0]
0x18001d732  mov     ecx, r13d; Size
0x18001d735  mov     rax, [rdi]
0x18001d738  mov     rsi, [rax+50h]
0x18001d73c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d741  lea     rcx, [rbp+5E0h+var_450]; psz
0x18001d748  mov     rbx, rax
0x18001d74b  mov     qword ptr [rax+8], 0
0x18001d753  mov     dword ptr [rax+10h], 1
0x18001d75a  call    cs:__imp_SysAllocString
0x18001d760  mov     [rbx], rax
0x18001d763  test    rax, rax
0x18001d766  jz      loc_18001D8E3
0x18001d76c  mov     rdx, rax
0x18001d76f  mov     [rsp+6E0h+var_6C0], rbx
0x18001d774  mov     rax, rsi
0x18001d777  mov     rcx, rdi
0x18001d77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d77f  lea     rcx, [rsp+6E0h+var_6C0]; this
0x18001d784  mov     ebx, eax
0x18001d786  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001d78b  test    ebx, ebx
0x18001d78d  jmp     loc_18001D818
0x18001d792  mov     ebx, 80070216h
0x18001d797  mov     rcx, [rsp+6E0h+var_6B0]
0x18001d79c  test    rcx, rcx
0x18001d79f  jz      short loc_18001D7AD
0x18001d7a1  mov     rax, [rcx]
0x18001d7a4  mov     rax, [rax+10h]
0x18001d7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ad  mov     rcx, [rsp+6E0h+var_6A8]
0x18001d7b2  test    rcx, rcx
0x18001d7b5  jz      short loc_18001D7C3
0x18001d7b7  mov     rax, [rcx]
0x18001d7ba  mov     rax, [rax+10h]
0x18001d7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7c3  mov     rcx, [rsp+6E0h+var_6A0]
0x18001d7c8  test    rcx, rcx
0x18001d7cb  jz      short loc_18001D7D9
0x18001d7cd  mov     rax, [rcx]
0x18001d7d0  mov     rax, [rax+10h]
0x18001d7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d9  mov     eax, ebx
0x18001d7db  mov     rcx, [rbp+5E0h+var_30]
0x18001d7e2  xor     rcx, rsp; StackCookie
0x18001d7e5  call    __security_check_cookie
0x18001d7ea  lea     r11, [rsp+6E0h+var_20]
0x18001d7f2  mov     rbx, [r11+38h]
0x18001d7f6  mov     rsi, [r11+40h]
0x18001d7fa  mov     rsp, r11
0x18001d7fd  pop     r15
0x18001d7ff  pop     r14
0x18001d801  pop     r13
0x18001d803  pop     rdi
0x18001d804  pop     rbp
0x18001d805  retn
0x18001d806  mov     r8, [rcx]
0x18001d809  xor     edx, edx
0x18001d80b  mov     rax, [r8+60h]
0x18001d80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d814  mov     ebx, eax
0x18001d816  test    eax, eax
0x18001d818  js      loc_18001D797
0x18001d81e  mov     eax, 88888889h
0x18001d823  mul     r15d
0x18001d826  mov     eax, 0AAAAAAABh
0x18001d82b  mov     r9d, edx
0x18001d82e  shr     r9d, 5
0x18001d832  mul     r9d
0x18001d835  movzx   ecx, r9w
0x18001d839  shr     edx, 4
0x18001d83c  movzx   eax, dx
0x18001d83f  imul    r8d, ecx, 3Ch ; '<'
0x18001d843  add     ax, ax
0x18001d846  mov     word ptr [rsp+6E0h+var_688+6], dx
0x18001d84b  lea     ecx, [rax+rdx]
0x18001d84e  sub     r15w, r8w
0x18001d852  shl     cx, 3
0x18001d856  lea     rdx, [rbp+5E0h+var_240]
0x18001d85d  sub     r9w, cx
0x18001d861  mov     word ptr [rsp+6E0h+var_688+0Ah], r15w
0x18001d867  xor     eax, eax
0x18001d869  mov     word ptr [rsp+6E0h+var_688+8], r9w
0x18001d86f  lea     rcx, [rsp+6E0h+var_688]
0x18001d874  mov     dword ptr [rsp+6E0h+var_688], eax
0x18001d878  call    CreateScheduleTimeString
0x18001d87d  mov     ebx, eax
0x18001d87f  test    eax, eax
0x18001d881  js      loc_18001D797
0x18001d887  mov     rdi, [rsp+6E0h+var_6B0]
0x18001d88c  mov     rcx, r13; Size
0x18001d88f  mov     rsi, [rdi]
0x18001d892  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d897  lea     rcx, [rbp+5E0h+var_240]; psz
0x18001d89e  mov     rbx, rax
0x18001d8a1  mov     qword ptr [rax+8], 0
0x18001d8a9  mov     dword ptr [rax+10h], 1
0x18001d8b0  call    cs:__imp_SysAllocString
0x18001d8b6  mov     [rbx], rax
0x18001d8b9  test    rax, rax
0x18001d8bc  jz      short loc_18001D8E3
0x18001d8be  mov     rdx, rax
0x18001d8c1  mov     [rsp+6E0h+var_6C0], rbx
0x18001d8c6  mov     rax, [rsi+40h]
0x18001d8ca  mov     rcx, rdi
0x18001d8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d2  lea     rcx, [rsp+6E0h+var_6C0]; this
0x18001d8d7  mov     ebx, eax
0x18001d8d9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001d8de  jmp     loc_18001D797
0x18001d8e3  mov     ecx, 8007000Eh; int
0x18001d8e8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
