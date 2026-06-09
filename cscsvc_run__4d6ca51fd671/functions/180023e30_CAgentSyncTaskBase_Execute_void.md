# CAgentSyncTaskBase::Execute(void)

- ea: `0x180023e30`
- end: `0x180024019`
- name: `?Execute@CAgentSyncTaskBase@@UEAAXXZ`
- size: `489`
- prototype: `void __fastcall(CAgentSyncTaskBase *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000bac8`
- `0x180023e30`
- `0x180024020`
- `0x180024410`
- `0x18003c460`
- `0x18003c488`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fc1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180023ef2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180023ef2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023f73`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023f73`

## pseudocode

```c
void __fastcall CAgentSyncTaskBase::Execute(CAgentSyncTaskBase *this)
{
  unsigned int v2; // edi
  int v3; // edx
  HANDLE *v4; // rsi
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // edx
  int v9; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_1b2e11bf501d36099a40201e41f6b5dd_Traceguids,
      (char *)this + 20);
  v2 = (*(__int64 (__fastcall **)(CAgentSyncTaskBase *, _QWORD))(*(_QWORD *)this + 128LL))(this, 0);
  if ( v2 && (*(unsigned int (__fastcall **)(CAgentSyncTaskBase *))(*(_QWORD *)this + 80LL))(this) )
  {
    EventDispatcherRcv_BackgroundSyncBegin(v2, v3);
    (*(void (__fastcall **)(CAgentSyncTaskBase *, _QWORD))(*(_QWORD *)this + 144LL))(this, 0);
    v9 = 0;
    v4 = (HANDLE *)((char *)this + 152);
    while ( !(*(unsigned int (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 18) + 8LL))(
               *((_QWORD *)this + 18),
               (char *)this + 152) )
    {
      if ( ImpersonateLoggedOnUser(*v4) )
      {
        (*(void (__fastcall **)(CAgentSyncTaskBase *, __int64))(*(_QWORD *)this + 144LL))(this, 1);
        if ( (*(unsigned int (__fastcall **)(CAgentSyncTaskBase *))(*(_QWORD *)this + 136LL))(this) )
          v5 = (*(__int64 (__fastcall **)(CAgentSyncTaskBase *, __int64))(*(_QWORD *)this + 128LL))(this, 1);
        else
          v5 = v2;
        CAgentSyncTaskBase::_SynchronizePaths(this, v5, &v9);
        (*(void (__fastcall **)(CAgentSyncTaskBase *, _QWORD, __int64))(*(_QWORD *)this + 152LL))(
          this,
          (unsigned int)v9,
          1);
        RevertToSelf();
        v6 = (unsigned int)v9;
        if ( v9 )
        {
          v7 = *((_QWORD *)this + 14);
          if ( *(_DWORD *)(v7 + 44) )
          {
            *(_DWORD *)(v7 + 44) = 0;
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1b2e11bf501d36099a40201e41f6b5dd_Traceguids);
            }
            v6 = 0;
            v9 = 0;
          }
        }
      }
      else
      {
        GetLastError();
        v6 = (unsigned int)v9;
      }
      *v4 = 0;
      if ( (_DWORD)v6 )
        goto LABEL_22;
    }
    v6 = (unsigned int)v9;
LABEL_22:
    (*(void (__fastcall **)(CAgentSyncTaskBase *, __int64, _QWORD))(*(_QWORD *)this + 152LL))(this, v6, 0);
    EventDispatcherRcv_BackgroundSyncEnd(v2, v8);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 16LL))(*((_QWORD *)this + 18));
  }
}

```

## disassembly

```asm
0x180023e30  push    rbx
0x180023e32  push    rsi
0x180023e33  push    rdi
0x180023e34  push    r14
0x180023e36  sub     rsp, 28h
0x180023e3a  mov     rbx, rcx
0x180023e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e44  lea     r14, WPP_GLOBAL_Control
0x180023e4b  cmp     rcx, r14
0x180023e4e  jz      short loc_180023E72
0x180023e50  test    dword ptr [rcx+1Ch], 400h
0x180023e57  jz      short loc_180023E72
0x180023e59  mov     rcx, [rcx+10h]
0x180023e5d  lea     r9, [rbx+14h]
0x180023e61  mov     edx, 0Bh
0x180023e66  lea     r8, WPP_1b2e11bf501d36099a40201e41f6b5dd_Traceguids
0x180023e6d  call    WPP_SF_S
0x180023e72  mov     rax, [rbx]
0x180023e75  xor     edx, edx
0x180023e77  mov     rcx, rbx
0x180023e7a  mov     rax, [rax+80h]
0x180023e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e86  mov     edi, eax
0x180023e88  test    eax, eax
0x180023e8a  jz      loc_18002400F
0x180023e90  mov     rcx, [rbx]
0x180023e93  mov     rax, [rcx+50h]
0x180023e97  mov     rcx, rbx
0x180023e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e9f  test    eax, eax
0x180023ea1  jz      loc_18002400F
0x180023ea7  mov     ecx, edi; unsigned int
0x180023ea9  call    ?EventDispatcherRcv_BackgroundSyncBegin@@YAJKH@Z; EventDispatcherRcv_BackgroundSyncBegin(ulong,int)
0x180023eae  mov     rax, [rbx]
0x180023eb1  xor     edx, edx
0x180023eb3  mov     rcx, rbx
0x180023eb6  mov     rax, [rax+90h]
0x180023ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ec2  mov     [rsp+48h+arg_0], 0
0x180023eca  lea     rsi, [rbx+98h]
0x180023ed1  mov     rcx, [rbx+90h]
0x180023ed8  mov     rdx, rsi
0x180023edb  mov     rax, [rcx]
0x180023ede  mov     rax, [rax+8]
0x180023ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ee7  test    eax, eax
0x180023ee9  jnz     loc_180023FDC
0x180023eef  mov     rcx, [rsi]; hToken
0x180023ef2  call    cs:__imp_ImpersonateLoggedOnUser
0x180023ef8  test    eax, eax
0x180023efa  jz      loc_180023FC1
0x180023f00  mov     rax, [rbx]
0x180023f03  mov     edx, 1
0x180023f08  mov     rcx, rbx
0x180023f0b  mov     rax, [rax+90h]
0x180023f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f17  mov     rax, [rbx]
0x180023f1a  mov     rcx, rbx
0x180023f1d  mov     rax, [rax+88h]
0x180023f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f29  test    eax, eax
0x180023f2b  jz      short loc_180023F46
0x180023f2d  mov     rax, [rbx]
0x180023f30  mov     edx, 1
0x180023f35  mov     rcx, rbx
0x180023f38  mov     rax, [rax+80h]
0x180023f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f44  jmp     short loc_180023F48
0x180023f46  mov     eax, edi
0x180023f48  lea     r8, [rsp+48h+arg_0]; int *
0x180023f4d  mov     edx, eax; unsigned int
0x180023f4f  mov     rcx, rbx; this
0x180023f52  call    ?_SynchronizePaths@CAgentSyncTaskBase@@AEAAXKPEAH@Z; CAgentSyncTaskBase::_SynchronizePaths(ulong,int *)
0x180023f57  mov     rax, [rbx]
0x180023f5a  mov     r8d, 1
0x180023f60  mov     edx, [rsp+48h+arg_0]
0x180023f64  mov     rcx, rbx
0x180023f67  mov     rax, [rax+98h]
0x180023f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f73  call    cs:__imp_RevertToSelf
0x180023f79  mov     edx, [rsp+48h+arg_0]
0x180023f7d  test    edx, edx
0x180023f7f  jz      short loc_180023FCB
0x180023f81  mov     rax, [rbx+70h]
0x180023f85  cmp     dword ptr [rax+2Ch], 0
0x180023f89  jz      short loc_180023FCB
0x180023f8b  mov     dword ptr [rax+2Ch], 0
0x180023f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f99  cmp     rcx, r14
0x180023f9c  jz      short loc_180023FB9
0x180023f9e  test    byte ptr [rcx+1Ch], 20h
0x180023fa2  jz      short loc_180023FB9
0x180023fa4  mov     rcx, [rcx+10h]
0x180023fa8  lea     r8, WPP_1b2e11bf501d36099a40201e41f6b5dd_Traceguids
0x180023faf  mov     edx, 0Ch
0x180023fb4  call    WPP_SF_
0x180023fb9  xor     edx, edx
0x180023fbb  mov     [rsp+48h+arg_0], edx
0x180023fbf  jmp     short loc_180023FCB
0x180023fc1  call    cs:__imp_GetLastError
0x180023fc7  mov     edx, [rsp+48h+arg_0]
0x180023fcb  mov     qword ptr [rsi], 0
0x180023fd2  test    edx, edx
0x180023fd4  jz      loc_180023ED1
0x180023fda  jmp     short loc_180023FE0
0x180023fdc  mov     edx, [rsp+48h+arg_0]
0x180023fe0  mov     rax, [rbx]
0x180023fe3  xor     r8d, r8d
0x180023fe6  mov     rcx, rbx
0x180023fe9  mov     rax, [rax+98h]
0x180023ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ff5  mov     ecx, edi; unsigned int
0x180023ff7  call    ?EventDispatcherRcv_BackgroundSyncEnd@@YAJKH@Z; EventDispatcherRcv_BackgroundSyncEnd(ulong,int)
0x180023ffc  mov     rcx, [rbx+90h]
0x180024003  mov     rax, [rcx]
0x180024006  mov     rax, [rax+10h]
0x18002400a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002400f  add     rsp, 28h
0x180024013  pop     r14
0x180024015  pop     rdi
0x180024016  pop     rsi
0x180024017  pop     rbx
0x180024018  retn
```
