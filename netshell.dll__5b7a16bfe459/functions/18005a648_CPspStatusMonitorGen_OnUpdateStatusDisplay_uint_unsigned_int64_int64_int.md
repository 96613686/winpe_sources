# CPspStatusMonitorGen::OnUpdateStatusDisplay(uint,unsigned __int64,__int64,int &)

- ea: `0x18005a648`
- end: `0x18005a724`
- name: `?OnUpdateStatusDisplay@CPspStatusMonitorGen@@QEAA_JI_K_JAEAH@Z`
- size: `220`
- prototype: `__int64 __fastcall(CPspStatusMonitorGen *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180054180`

## callees

- `0x18000a730`
- `0x18000a810`
- `0x18005a648`
- `0x18005ae60`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005a6f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005a6f7`
- `ole32!CoTaskMemFree` at `0x18005a708`
- `ole32!CoTaskMemFree` at `0x18005a708`

## pseudocode

```c
__int64 __fastcall CPspStatusMonitorGen::OnUpdateStatusDisplay(
        CPspStatusMonitorGen *this,
        __int64 a2,
        struct tagSTATMON_ENGINEDATA *a3,
        unsigned int a4)
{
  __int64 v6; // rcx
  struct tagSTATMON_ENGINEDATA *v7; // rax
  struct tagSTATMON_ENGINEDATA *v8; // rdx
  __int64 v9; // rdi
  ULONGLONG TickCount64; // rax
  void *v11; // rcx
  struct tagSTATMON_ENGINEDATA *v13; // [rsp+40h] [rbp+18h] BYREF

  v13 = a3;
  if ( *((_DWORD *)this + 25) )
  {
    v6 = *((_QWORD *)this + 11) + 32LL;
    v13 = 0;
    if ( (*(int (__fastcall **)(__int64, struct tagSTATMON_ENGINEDATA **))(*(_QWORD *)v6 + 104LL))(v6, &v13) >= 0 )
    {
      v7 = v13;
      if ( v13 )
      {
        v8 = (struct tagSTATMON_ENGINEDATA *)*((_QWORD *)this + 10);
        if ( v8 )
        {
          CPspStatusMonitorGen::UpdatePage(this, v8, v13);
          (*(void (__fastcall **)(CPspStatusMonitorGen *, _QWORD))(*(_QWORD *)this + 40LL))(this, a4);
          v9 = *((_QWORD *)this + 11);
          if ( *(_DWORD *)(v9 + 156) == 2
            && (*(_QWORD *)(v9 + 288)
             || (int)CWlanStatEngine::GetWlanConnectionAttributes(*((CWlanStatEngine **)this + 11)) >= 0) )
          {
            CPspStatusMonitorGen::UpdateSignalQualityIcon(this, *(_DWORD *)(*(_QWORD *)(v9 + 288) + 576LL));
          }
          TickCount64 = GetTickCount64();
          v11 = (void *)*((_QWORD *)this + 10);
          *((_QWORD *)this + 16) = TickCount64;
          CoTaskMemFree(v11);
          v7 = v13;
        }
        *((_QWORD *)this + 10) = v7;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005a648  mov     r11, rsp
0x18005a64b  mov     [r11+8], rbx
0x18005a64f  mov     [r11+18h], r8
0x18005a653  push    rdi
0x18005a654  sub     rsp, 20h
0x18005a658  cmp     dword ptr [rcx+64h], 0
0x18005a65c  mov     rdi, r9
0x18005a65f  mov     rbx, rcx
0x18005a662  jz      loc_18005A717
0x18005a668  mov     rcx, [rcx+58h]
0x18005a66c  lea     rdx, [r11+18h]
0x18005a670  add     rcx, 20h ; ' '
0x18005a674  mov     qword ptr [r11+18h], 0
0x18005a67c  mov     rax, [rcx]
0x18005a67f  mov     rax, [rax+68h]
0x18005a683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a688  test    eax, eax
0x18005a68a  js      loc_18005A717
0x18005a690  mov     rax, [rsp+28h+arg_10]
0x18005a695  test    rax, rax
0x18005a698  jz      short loc_18005A717
0x18005a69a  mov     rdx, [rbx+50h]; struct tagSTATMON_ENGINEDATA *
0x18005a69e  test    rdx, rdx
0x18005a6a1  jz      short loc_18005A713
0x18005a6a3  mov     r8, rax; struct tagSTATMON_ENGINEDATA *
0x18005a6a6  mov     rcx, rbx; this
0x18005a6a9  call    ?UpdatePage@CPspStatusMonitorGen@@IEAAXPEAUtagSTATMON_ENGINEDATA@@PEBU2@@Z; CPspStatusMonitorGen::UpdatePage(tagSTATMON_ENGINEDATA *,tagSTATMON_ENGINEDATA const *)
0x18005a6ae  mov     rax, [rbx]
0x18005a6b1  mov     edx, edi
0x18005a6b3  mov     rcx, rbx
0x18005a6b6  mov     rax, [rax+28h]
0x18005a6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a6bf  mov     rdi, [rbx+58h]
0x18005a6c3  cmp     dword ptr [rdi+9Ch], 2
0x18005a6ca  jnz     short loc_18005A6F7
0x18005a6cc  cmp     qword ptr [rdi+120h], 0
0x18005a6d4  jnz     short loc_18005A6E2
0x18005a6d6  mov     rcx, rdi; this
0x18005a6d9  call    ?GetWlanConnectionAttributes@CWlanStatEngine@@IEAAJXZ; CWlanStatEngine::GetWlanConnectionAttributes(void)
0x18005a6de  test    eax, eax
0x18005a6e0  js      short loc_18005A6F7
0x18005a6e2  mov     rdx, [rdi+120h]
0x18005a6e9  mov     rcx, rbx; this
0x18005a6ec  mov     edx, [rdx+240h]; unsigned int
0x18005a6f2  call    ?UpdateSignalQualityIcon@CPspStatusMonitorGen@@IEAAXK@Z; CPspStatusMonitorGen::UpdateSignalQualityIcon(ulong)
0x18005a6f7  call    cs:__imp_GetTickCount64
0x18005a6fd  mov     rcx, [rbx+50h]; pv
0x18005a701  mov     [rbx+80h], rax
0x18005a708  call    cs:__imp_CoTaskMemFree
0x18005a70e  mov     rax, [rsp+28h+arg_10]
0x18005a713  mov     [rbx+50h], rax
0x18005a717  mov     rbx, [rsp+28h+arg_0]
0x18005a71c  xor     eax, eax
0x18005a71e  add     rsp, 20h
0x18005a722  pop     rdi
0x18005a723  retn
```
