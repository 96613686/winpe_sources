# CMachineSettings::OnUpdateStore(void)

- ea: `0x180036090`
- end: `0x18003633e`
- name: `?OnUpdateStore@CMachineSettings@@UEAAJXZ`
- size: `686`
- prototype: `__int64 __fastcall(CMachineSettings *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18002cd50`
- `0x1800353ac`
- `0x180035590`
- `0x18003588c`
- `0x180036090`
- `0x180036a60`
- `0x180053f3c`
- `0x180054424`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!UpdateDCOMSettings` at `0x180036322`
- `api-ms-win-core-com-private-l1-1-0!UpdateDCOMSettings` at `0x180036322`
- `ADVAPI32!RegDeleteKeyW` at `0x1800362fd`
- `ADVAPI32!RegDeleteKeyW` at `0x1800362fd`

## pseudocode

```c
__int64 __fastcall CMachineSettings::OnUpdateStore(CMachineSettings *this)
{
  int updated; // edi
  int j; // esi
  int i; // esi
  int v5; // eax
  int v6; // eax
  int v8; // [rsp+80h] [rbp+38h] BYREF
  unsigned int v9; // [rsp+88h] [rbp+40h] BYREF
  int v10; // [rsp+90h] [rbp+48h] BYREF
  __int64 v11; // [rsp+98h] [rbp+50h] BYREF

  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  if ( *((_DWORD *)this + 32) || *((_QWORD *)this + 15) )
    return 2147942487LL;
  CRegistryKeyCache::FlushCache(*((CRegistryKeyCache **)this + 35));
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 59) = 0;
  updated = CSimpleDataTableCursor::InternalRestartWriteRow((CMachineSettings *)((char *)this + 40));
  while ( updated >= 0 )
  {
    updated = CSimpleDataTableCursor::InternalMoveToNextWriteRow((CMachineSettings *)((char *)this + 40), &v9);
    if ( updated )
      break;
    switch ( v9 )
    {
      case 1u:
        updated = (*(__int64 (__fastcall **)(CMachineSettings *))(*(_QWORD *)this + 184LL))(this);
        for ( i = 0; i < 32; ++i )
        {
          if ( updated < 0 )
            break;
          updated = (*(__int64 (__fastcall **)(CMachineSettings *, _QWORD, int *, _QWORD, int *, __int64 *))(*(_QWORD *)this + 152LL))(
                      this,
                      (unsigned int)i,
                      &v8,
                      0,
                      &v10,
                      &v11);
          if ( updated >= 0 && (v8 & 2) != 0 )
            updated = CMachineSettings::UpdateColumn(this, i, 1u);
        }
        break;
      case 2u:
        updated = (*(__int64 (__fastcall **)(CMachineSettings *))(*(_QWORD *)this + 184LL))(this);
        if ( updated < 0 )
          goto LABEL_39;
        updated = (*(__int64 (__fastcall **)(CMachineSettings *))(*(_QWORD *)this + 200LL))(this);
        if ( updated < 0 )
          goto LABEL_39;
        for ( j = 0; j < 32; ++j )
        {
          if ( updated < 0 )
            break;
          updated = (*(__int64 (__fastcall **)(CMachineSettings *, _QWORD, int *, _QWORD, int *, __int64 *))(*(_QWORD *)this + 152LL))(
                      this,
                      (unsigned int)j,
                      &v8,
                      0,
                      &v10,
                      &v11);
          if ( updated >= 0 && (v8 & 2) != 0 )
            updated = CMachineSettings::UpdateColumn(this, j, 2u);
        }
        break;
      case 3u:
        updated = CMachineSettings::DoLowerUpdateIfNeeded(this, updated + 3);
        break;
    }
    if ( *((_DWORD *)this + 59) )
    {
      UploadSQMData<enum CatalogServerSQMFlags>(32);
      if ( updated >= 0 )
        updated = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 144LL))(*((_QWORD *)this + 26));
      *((_DWORD *)this + 59) = 0;
    }
  }
  v5 = 0;
  if ( updated != -2146367487 )
    v5 = updated;
  updated = v5;
  if ( v5 >= 0 )
  {
    updated = 0;
    if ( *((_DWORD *)this + 56) )
    {
      if ( !*((_DWORD *)this + 59)
        || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 144LL))(*((_QWORD *)this + 26)),
            *((_DWORD *)this + 59) = 0,
            updated = v6,
            v6 >= 0) )
      {
        updated = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 96LL))(*((_QWORD *)this + 26));
      }
      *((_DWORD *)this + 56) = 0;
    }
  }
  if ( *((_DWORD *)this + 60) )
  {
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Rpc\\Internet");
    *((_DWORD *)this + 60) = 0;
  }
LABEL_39:
  CRegistryKeyCache::FlushCache(*((CRegistryKeyCache **)this + 35));
  CTmpMemoryCache::ClearCache(*((CTmpMemoryCache **)this + 36));
  UpdateDCOMSettings();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180036090  push    rbp
0x180036092  push    rbx
0x180036093  push    rsi
0x180036094  push    rdi
0x180036095  push    r14
0x180036097  push    r15
0x180036099  mov     rbp, rsp
0x18003609c  sub     rsp, 48h
0x1800360a0  xor     r15d, r15d
0x1800360a3  mov     rbx, rcx
0x1800360a6  mov     [rbp+arg_8], r15d
0x1800360aa  mov     [rbp+arg_0], r15d
0x1800360ae  mov     [rbp+arg_10], r15d
0x1800360b2  mov     [rbp+arg_18], r15
0x1800360b6  cmp     [rcx+80h], r15d
0x1800360bd  jnz     loc_18003632C
0x1800360c3  cmp     [rcx+78h], r15
0x1800360c7  jnz     loc_18003632C
0x1800360cd  mov     rcx, [rcx+118h]; this
0x1800360d4  call    ?FlushCache@CRegistryKeyCache@@QEAAXXZ; CRegistryKeyCache::FlushCache(void)
0x1800360d9  lea     rcx, [rbx+28h]; this
0x1800360dd  mov     [rbx+0E0h], r15d
0x1800360e4  mov     [rbx+0ECh], r15d
0x1800360eb  call    ?InternalRestartWriteRow@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InternalRestartWriteRow(void)
0x1800360f0  mov     edi, eax
0x1800360f2  test    edi, edi
0x1800360f4  js      loc_180036280
0x1800360fa  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800360fe  lea     rcx, [rbx+28h]; this
0x180036102  call    ?InternalMoveToNextWriteRow@CSimpleDataTableCursor@@QEAAJPEAK@Z; CSimpleDataTableCursor::InternalMoveToNextWriteRow(ulong *)
0x180036107  mov     edi, eax
0x180036109  test    eax, eax
0x18003610b  jnz     loc_180036280
0x180036111  mov     eax, [rbp+arg_8]
0x180036114  sub     eax, 1
0x180036117  jz      loc_1800361D4
0x18003611d  sub     eax, 1
0x180036120  jz      short loc_18003613D
0x180036122  cmp     eax, 1
0x180036125  jnz     loc_180036241
0x18003612b  lea     edx, [rdi+3]; unsigned int
0x18003612e  mov     rcx, rbx; this
0x180036131  call    ?DoLowerUpdateIfNeeded@CMachineSettings@@QEAAJK@Z; CMachineSettings::DoLowerUpdateIfNeeded(ulong)
0x180036136  mov     edi, eax
0x180036138  jmp     loc_180036241
0x18003613d  mov     rax, [rbx]
0x180036140  mov     rcx, rbx
0x180036143  mov     rax, [rax+0B8h]
0x18003614a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003614f  mov     edi, eax
0x180036151  test    eax, eax
0x180036153  js      loc_18003630A
0x180036159  mov     rax, [rbx]
0x18003615c  mov     rcx, rbx
0x18003615f  mov     rax, [rax+0C8h]
0x180036166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003616b  mov     edi, eax
0x18003616d  test    eax, eax
0x18003616f  js      loc_18003630A
0x180036175  mov     esi, r15d
0x180036178  test    edi, edi
0x18003617a  js      loc_180036241
0x180036180  mov     rax, [rbx]
0x180036183  lea     rcx, [rbp+arg_18]
0x180036187  mov     [rsp+48h+var_20], rcx
0x18003618c  lea     r8, [rbp+arg_0]
0x180036190  lea     rcx, [rbp+arg_10]
0x180036194  xor     r9d, r9d
0x180036197  mov     [rsp+48h+var_28], rcx
0x18003619c  mov     edx, esi
0x18003619e  mov     rax, [rax+98h]
0x1800361a5  mov     rcx, rbx
0x1800361a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361ad  mov     edi, eax
0x1800361af  test    eax, eax
0x1800361b1  js      short loc_1800361CB
0x1800361b3  test    byte ptr [rbp+arg_0], 2
0x1800361b7  jz      short loc_1800361CB
0x1800361b9  mov     r8d, 2; unsigned int
0x1800361bf  mov     edx, esi; int
0x1800361c1  mov     rcx, rbx; this
0x1800361c4  call    ?UpdateColumn@CMachineSettings@@QEAAJHK@Z; CMachineSettings::UpdateColumn(int,ulong)
0x1800361c9  mov     edi, eax
0x1800361cb  inc     esi
0x1800361cd  cmp     esi, 20h ; ' '
0x1800361d0  jl      short loc_180036178
0x1800361d2  jmp     short loc_180036241
0x1800361d4  mov     rax, [rbx]
0x1800361d7  mov     rcx, rbx
0x1800361da  mov     rax, [rax+0B8h]
0x1800361e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361e6  mov     edi, eax
0x1800361e8  mov     esi, r15d
0x1800361eb  test    edi, edi
0x1800361ed  js      short loc_180036241
0x1800361ef  mov     rax, [rbx]
0x1800361f2  lea     rcx, [rbp+arg_18]
0x1800361f6  mov     [rsp+48h+var_20], rcx
0x1800361fb  lea     r8, [rbp+arg_0]
0x1800361ff  lea     rcx, [rbp+arg_10]
0x180036203  xor     r9d, r9d
0x180036206  mov     [rsp+48h+var_28], rcx
0x18003620b  mov     edx, esi
0x18003620d  mov     rax, [rax+98h]
0x180036214  mov     rcx, rbx
0x180036217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003621c  mov     edi, eax
0x18003621e  test    eax, eax
0x180036220  js      short loc_18003623A
0x180036222  test    byte ptr [rbp+arg_0], 2
0x180036226  jz      short loc_18003623A
0x180036228  mov     r8d, 1; unsigned int
0x18003622e  mov     edx, esi; int
0x180036230  mov     rcx, rbx; this
0x180036233  call    ?UpdateColumn@CMachineSettings@@QEAAJHK@Z; CMachineSettings::UpdateColumn(int,ulong)
0x180036238  mov     edi, eax
0x18003623a  inc     esi
0x18003623c  cmp     esi, 20h ; ' '
0x18003623f  jl      short loc_1800361EB
0x180036241  cmp     [rbx+0ECh], r15d
0x180036248  jz      loc_1800360F2
0x18003624e  mov     ecx, 20h ; ' '
0x180036253  call    ??$UploadSQMData@W4CatalogServerSQMFlags@@@@YAXW4CatalogServerSQMFlags@@@Z; UploadSQMData<CatalogServerSQMFlags>(CatalogServerSQMFlags)
0x180036258  test    edi, edi
0x18003625a  js      short loc_180036274
0x18003625c  mov     rcx, [rbx+0D0h]
0x180036263  mov     rax, [rcx]
0x180036266  mov     rax, [rax+90h]
0x18003626d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036272  mov     edi, eax
0x180036274  mov     [rbx+0ECh], r15d
0x18003627b  jmp     loc_1800360F2
0x180036280  cmp     edi, 80110801h
0x180036286  mov     eax, r15d
0x180036289  cmovnz  eax, edi
0x18003628c  mov     edi, eax
0x18003628e  test    eax, eax
0x180036290  js      short loc_1800362E6
0x180036292  mov     edi, r15d
0x180036295  cmp     [rbx+0E0h], r15d
0x18003629c  jz      short loc_1800362E6
0x18003629e  cmp     [rbx+0ECh], r15d
0x1800362a5  jz      short loc_1800362CA
0x1800362a7  mov     rcx, [rbx+0D0h]
0x1800362ae  mov     rax, [rcx]
0x1800362b1  mov     rax, [rax+90h]
0x1800362b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362bd  mov     [rbx+0ECh], r15d
0x1800362c4  mov     edi, eax
0x1800362c6  test    eax, eax
0x1800362c8  js      short loc_1800362DF
0x1800362ca  mov     rcx, [rbx+0D0h]
0x1800362d1  mov     rax, [rcx]
0x1800362d4  mov     rax, [rax+60h]
0x1800362d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362dd  mov     edi, eax
0x1800362df  mov     [rbx+0E0h], r15d
0x1800362e6  cmp     [rbx+0F0h], r15d
0x1800362ed  jz      short loc_18003630A
0x1800362ef  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Rpc\\Internet"
0x1800362f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800362fd  call    cs:__imp_RegDeleteKeyW
0x180036303  mov     [rbx+0F0h], r15d
0x18003630a  mov     rcx, [rbx+118h]; this
0x180036311  call    ?FlushCache@CRegistryKeyCache@@QEAAXXZ; CRegistryKeyCache::FlushCache(void)
0x180036316  mov     rcx, [rbx+120h]; this
0x18003631d  call    ?ClearCache@CTmpMemoryCache@@QEAAXXZ; CTmpMemoryCache::ClearCache(void)
0x180036322  call    cs:__imp_UpdateDCOMSettings
0x180036328  mov     eax, edi
0x18003632a  jmp     short loc_180036331
0x18003632c  mov     eax, 80070057h
0x180036331  add     rsp, 48h
0x180036335  pop     r15
0x180036337  pop     r14
0x180036339  pop     rdi
0x18003633a  pop     rsi
0x18003633b  pop     rbx
0x18003633c  pop     rbp
0x18003633d  retn
```
