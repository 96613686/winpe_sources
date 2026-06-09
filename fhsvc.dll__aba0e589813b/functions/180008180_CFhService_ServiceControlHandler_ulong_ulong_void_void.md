# CFhService::ServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x180008180`
- end: `0x180008544`
- name: `?ServiceControlHandler@CFhService@@CAKKKPEAX0@Z`
- size: `964`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, unsigned int *lpEventData, int *lpContext)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180001200`
- `0x1800012d0`
- `0x180001f20`
- `0x180003190`
- `0x180008180`
- `0x1800096c0`
- `0x18000ac48`
- `0x18000ca14`
- `0x18000d840`
- `0x18000d868`
- `0x18000d8ac`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x18000827f`
- `ADVAPI32!SetServiceStatus` at `0x18000827f`
- `KERNEL32!GetLastError` at `0x18000829b`
- `KERNEL32!GetLastError` at `0x18000829b`
- `KERNEL32!SetEvent` at `0x18000826b`
- `KERNEL32!SetEvent` at `0x18000826b`

## pseudocode

```c
__int64 __fastcall CFhService::ServiceControlHandler(
        DWORD dwControl,
        __int64 dwEventType,
        unsigned int *lpEventData,
        int *lpContext)
{
  __int64 v7; // rbp
  CManagerThread *v8; // rcx
  unsigned int v9; // edi
  signed int LastError; // eax
  CManagerThread *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // ecx
  CManagerThread *v14; // rcx
  __int64 v15; // rdx
  CManagerThread *v16; // rcx
  CManagerThread *v17; // rcx
  CManagerThread *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx

  v7 = (unsigned int)dwEventType;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_DDi(*((_QWORD *)WPP_GLOBAL_Control + 2), dwEventType, lpEventData, dwControl, dwEventType, lpContext[14]);
  _m_prefetchw(lpContext + 14);
  v8 = (CManagerThread *)(lpContext[14] | 1u);
  if ( (_InterlockedOr(lpContext + 14, 1u) & 2) != 0 )
  {
    v9 = 1115;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v20 = 43;
LABEL_61:
      WPP_SF_D(v19[2], v20, lpEventData, dwControl);
    }
  }
  else if ( dwControl == 11 )
  {
    CManagerThread::HandleDeviceEvent(v8, v7, lpEventData);
    v9 = 0;
  }
  else
  {
    v9 = 120;
    switch ( dwControl )
    {
      case 1u:
      case 5u:
        _InterlockedOr(lpContext + 14, 2u);
        if ( dwControl == 1 )
        {
          CFhService::ReportStatus((CFhService *)lpContext, 3, (int)lpEventData, 3, 0x7530u);
        }
        else
        {
          lpContext[20] = 1;
          CFhService::ReportStatus((CFhService *)lpContext, 3, (int)lpEventData, 4, 0x1388u);
        }
        SetEvent(*((HANDLE *)lpContext + 6));
        v9 = 0;
        break;
      case 4u:
        if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)lpContext, (LPSERVICE_STATUS)(lpContext + 2))
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids,
            (unsigned int)LastError);
        }
        goto LABEL_17;
      case 0xDu:
        if ( (_DWORD)v7 != 10 )
        {
          switch ( (_DWORD)v7 )
          {
            case 4:
              v14 = (CManagerThread *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_47;
              v15 = 38;
              break;
            case 0x12:
              v17 = (CManagerThread *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
              CManagerThread::SetBackupMoratorium(v17, 0x927C0u);
              goto LABEL_17;
            case 0x8013:
              v12 = *(_QWORD *)lpEventData - *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1;
              if ( *(_QWORD *)lpEventData == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 )
                v12 = *((_QWORD *)lpEventData + 1) - *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4;
              if ( v12 || lpEventData[4] != 4 )
                goto LABEL_17;
              v13 = lpEventData[5];
              if ( !v13 )
              {
                v16 = (CManagerThread *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
                CManagerThread::SetBackupMoratorium(v16, 0x2BF20u);
                goto LABEL_17;
              }
              if ( v13 != 1 )
              {
LABEL_17:
                v9 = 0;
                goto LABEL_62;
              }
              v14 = (CManagerThread *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              {
LABEL_47:
                CManagerThread::SetBackupMoratorium(v14, 0xFFFFFFFF);
                goto LABEL_17;
              }
              v15 = 40;
              break;
            default:
              goto LABEL_17;
          }
          WPP_SF_(*((_QWORD *)v14 + 2), v15, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
          goto LABEL_47;
        }
        CManagerThread::UpdatePowerState(v8);
        v9 = 0;
        break;
      case 0xEu:
        if ( (_DWORD)v7 != 5 )
          goto LABEL_17;
        v18 = (CManagerThread *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids,
            lpEventData[1]);
        CManagerThread::QueueBackupForLoggedOnUser(v18, lpEventData[1]);
        v9 = 0;
        break;
      case 0x20u:
        v11 = (CManagerThread *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
        CManagerThread::QueueBackupForAllLoggedOnUsers(v11);
        break;
      default:
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          break;
        v20 = 42;
        goto LABEL_61;
    }
  }
LABEL_62:
  _InterlockedAnd(lpContext + 14, 0xFFFFFFFE);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, lpEventData, v9);
  return v9;
}

```

## disassembly

```asm
0x180008180  sub     rsp, 48h
0x180008184  mov     [rsp+48h+arg_0], rbx
0x180008189  mov     rbx, r9
0x18000818c  mov     [rsp+48h+arg_8], rbp
0x180008191  mov     [rsp+48h+arg_10], rsi
0x180008196  mov     esi, ecx
0x180008198  mov     [rsp+48h+var_10], r14
0x18000819d  mov     r14, r8
0x1800081a0  mov     [rsp+48h+var_18], r15
0x1800081a5  mov     ebp, edx
0x1800081a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081ae  lea     r15, WPP_GLOBAL_Control
0x1800081b5  cmp     rcx, r15
0x1800081b8  jz      short loc_1800081D9
0x1800081ba  test    byte ptr [rcx+1Ch], 10h
0x1800081be  jz      short loc_1800081D9
0x1800081c0  movsxd  rax, dword ptr [r9+38h]
0x1800081c4  mov     r9d, esi
0x1800081c7  mov     rcx, [rcx+10h]
0x1800081cb  mov     [rsp+48h+var_20], rax
0x1800081d0  mov     [rsp+48h+var_28], ebp
0x1800081d4  call    WPP_SF_DDi
0x1800081d9  prefetchw byte ptr [rbx+38h]
0x1800081dd  mov     eax, [rbx+38h]
0x1800081e0  mov     ecx, eax
0x1800081e2  or      ecx, 1; this
0x1800081e5  lock cmpxchg [rbx+38h], ecx
0x1800081ea  jnz     short loc_1800081E0
0x1800081ec  mov     [rsp+48h+var_8], rdi
0x1800081f1  test    al, 2
0x1800081f3  jnz     loc_180008496
0x1800081f9  cmp     esi, 0Bh
0x1800081fc  jz      loc_180008487
0x180008202  lea     eax, [rsi-1]; switch 32 cases
0x180008205  mov     edi, 78h ; 'x'
0x18000820a  cmp     eax, 1Fh
0x18000820d  ja      def_18000822C; jumptable 000000018000822C default case, cases 2,3,6-12,15-31
0x180008213  lea     rdx, cs:180000000h
0x18000821a  movzx   eax, ds:(byte_180008524 - 180000000h)[rdx+rax]
0x180008222  mov     ecx, ds:(jpt_18000822C - 180000000h)[rdx+rax*4]
0x180008229  add     rcx, rdx; this
0x18000822c  jmp     rcx; switch jump
0x18000822e  lock or dword ptr [rbx+38h], 2; jumptable 000000018000822C cases 1,5
0x180008233  mov     edx, 3; unsigned int
0x180008238  mov     rcx, rbx; this
0x18000823b  cmp     esi, 1
0x18000823e  jnz     short loc_18000824D
0x180008240  mov     [rsp+48h+var_28], 7530h
0x180008248  mov     r9d, edx
0x18000824b  jmp     short loc_180008262
0x18000824d  mov     dword ptr [rbx+50h], 1
0x180008254  mov     r9d, 4; unsigned int
0x18000825a  mov     [rsp+48h+var_28], 1388h; unsigned int
0x180008262  call    ?ReportStatus@CFhService@@AEAAJKKKK@Z; CFhService::ReportStatus(ulong,ulong,ulong,ulong)
0x180008267  mov     rcx, [rbx+30h]; hEvent
0x18000826b  call    cs:__imp_SetEvent
0x180008271  xor     edi, edi
0x180008273  jmp     loc_1800084BE
0x180008278  mov     rcx, [rbx]; jumptable 000000018000822C case 4
0x18000827b  lea     rdx, [rbx+8]; lpServiceStatus
0x18000827f  call    cs:__imp_SetServiceStatus
0x180008285  test    eax, eax
0x180008287  jnz     short loc_1800082CC
0x180008289  mov     rax, cs:WPP_GLOBAL_Control
0x180008290  cmp     rax, r15
0x180008293  jz      short loc_1800082CC
0x180008295  test    byte ptr [rax+1Ch], 1
0x180008299  jz      short loc_1800082CC
0x18000829b  call    cs:__imp_GetLastError
0x1800082a1  test    eax, eax
0x1800082a3  jle     short loc_1800082AD
0x1800082a5  movzx   eax, ax
0x1800082a8  or      eax, 80070000h
0x1800082ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082b4  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800082bb  mov     edx, 23h ; '#'
0x1800082c0  mov     r9d, eax
0x1800082c3  mov     rcx, [rcx+10h]
0x1800082c7  call    WPP_SF_d
0x1800082cc  xor     edi, edi
0x1800082ce  jmp     loc_1800084BE
0x1800082d3  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018000822C case 32
0x1800082da  cmp     rcx, r15
0x1800082dd  jz      short loc_1800082FA
0x1800082df  test    byte ptr [rcx+1Ch], 8
0x1800082e3  jz      short loc_1800082FA
0x1800082e5  mov     rcx, [rcx+10h]
0x1800082e9  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800082f0  mov     edx, 24h ; '$'
0x1800082f5  call    WPP_SF_
0x1800082fa  call    ?QueueBackupForAllLoggedOnUsers@CManagerThread@@QEAAXXZ; CManagerThread::QueueBackupForAllLoggedOnUsers(void)
0x1800082ff  jmp     loc_1800084BE
0x180008304  cmp     ebp, 0Ah; jumptable 000000018000822C case 13
0x180008307  jz      loc_180008421
0x18000830d  cmp     ebp, 4
0x180008310  jz      loc_1800083EB
0x180008316  cmp     ebp, 12h
0x180008319  jz      loc_1800083B5
0x18000831f  cmp     ebp, 8013h
0x180008325  jnz     short loc_1800082CC
0x180008327  mov     rax, [r14]
0x18000832a  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180008331  jnz     short loc_18000833E
0x180008333  mov     rax, [r14+8]
0x180008337  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x18000833e  test    rax, rax
0x180008341  jnz     short loc_1800082CC
0x180008343  cmp     dword ptr [r14+10h], 4
0x180008348  jnz     short loc_1800082CC
0x18000834a  mov     ecx, [r14+14h]
0x18000834e  test    ecx, ecx
0x180008350  jz      short loc_18000837F
0x180008352  cmp     ecx, 1
0x180008355  jnz     loc_1800082CC
0x18000835b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008362  cmp     rcx, r15
0x180008365  jz      loc_180008412
0x18000836b  test    byte ptr [rcx+1Ch], 8
0x18000836f  jz      loc_180008412
0x180008375  mov     edx, 28h ; '('
0x18000837a  jmp     loc_180008402
0x18000837f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008386  cmp     rcx, r15
0x180008389  jz      short loc_1800083A6
0x18000838b  test    byte ptr [rcx+1Ch], 8
0x18000838f  jz      short loc_1800083A6
0x180008391  mov     rcx, [rcx+10h]
0x180008395  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x18000839c  mov     edx, 27h ; '''
0x1800083a1  call    WPP_SF_
0x1800083a6  mov     edx, 2BF20h; unsigned int
0x1800083ab  call    ?SetBackupMoratorium@CManagerThread@@QEAAXK@Z; CManagerThread::SetBackupMoratorium(ulong)
0x1800083b0  jmp     loc_1800082CC
0x1800083b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083bc  cmp     rcx, r15
0x1800083bf  jz      short loc_1800083DC
0x1800083c1  test    byte ptr [rcx+1Ch], 8
0x1800083c5  jz      short loc_1800083DC
0x1800083c7  mov     rcx, [rcx+10h]
0x1800083cb  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800083d2  mov     edx, 25h ; '%'
0x1800083d7  call    WPP_SF_
0x1800083dc  mov     edx, 927C0h; unsigned int
0x1800083e1  call    ?SetBackupMoratorium@CManagerThread@@QEAAXK@Z; CManagerThread::SetBackupMoratorium(ulong)
0x1800083e6  jmp     loc_1800082CC
0x1800083eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083f2  cmp     rcx, r15
0x1800083f5  jz      short loc_180008412
0x1800083f7  test    byte ptr [rcx+1Ch], 8
0x1800083fb  jz      short loc_180008412
0x1800083fd  mov     edx, 26h ; '&'
0x180008402  mov     rcx, [rcx+10h]
0x180008406  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x18000840d  call    WPP_SF_
0x180008412  mov     edx, 0FFFFFFFFh; unsigned int
0x180008417  call    ?SetBackupMoratorium@CManagerThread@@QEAAXK@Z; CManagerThread::SetBackupMoratorium(ulong)
0x18000841c  jmp     loc_1800082CC
0x180008421  call    ?UpdatePowerState@CManagerThread@@QEAAXXZ; CManagerThread::UpdatePowerState(void)
0x180008426  xor     edi, edi
0x180008428  jmp     loc_1800084BE
0x18000842d  cmp     ebp, 5; jumptable 000000018000822C case 14
0x180008430  jnz     loc_1800082CC
0x180008436  mov     rcx, cs:WPP_GLOBAL_Control
0x18000843d  cmp     rcx, r15
0x180008440  jz      short loc_180008461
0x180008442  test    byte ptr [rcx+1Ch], 8
0x180008446  jz      short loc_180008461
0x180008448  mov     r9d, [r14+4]
0x18000844c  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180008453  mov     rcx, [rcx+10h]
0x180008457  mov     edx, 29h ; ')'
0x18000845c  call    WPP_SF_d
0x180008461  mov     edx, [r14+4]; unsigned int
0x180008465  call    ?QueueBackupForLoggedOnUser@CManagerThread@@QEAAXK@Z; CManagerThread::QueueBackupForLoggedOnUser(ulong)
0x18000846a  xor     edi, edi
0x18000846c  jmp     short loc_1800084BE
0x18000846e  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018000822C default case, cases 2,3,6-12,15-31
0x180008475  cmp     rcx, r15
0x180008478  jz      short loc_1800084BE
0x18000847a  test    byte ptr [rcx+1Ch], 10h
0x18000847e  jz      short loc_1800084BE
0x180008480  mov     edx, 2Ah ; '*'
0x180008485  jmp     short loc_1800084B2
0x180008487  mov     rdx, rbp; unsigned __int64
0x18000848a  mov     r8, r14; void *
0x18000848d  call    ?HandleDeviceEvent@CManagerThread@@QEAAX_KPEAX@Z; CManagerThread::HandleDeviceEvent(unsigned __int64,void *)
0x180008492  xor     edi, edi
0x180008494  jmp     short loc_1800084BE
0x180008496  mov     edi, 45Bh
0x18000849b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084a2  cmp     rcx, r15
0x1800084a5  jz      short loc_1800084BE
0x1800084a7  test    byte ptr [rcx+1Ch], 2
0x1800084ab  jz      short loc_1800084BE
0x1800084ad  mov     edx, 2Bh ; '+'
0x1800084b2  mov     rcx, [rcx+10h]
0x1800084b6  mov     r9d, esi
0x1800084b9  call    WPP_SF_D
0x1800084be  lock and dword ptr [rbx+38h], 0FFFFFFFEh
0x1800084c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ca  mov     r14, [rsp+48h+var_10]
0x1800084cf  cmp     rcx, r15
0x1800084d2  mov     r15, [rsp+48h+var_18]
0x1800084d7  mov     rsi, [rsp+48h+arg_10]
0x1800084dc  mov     rbp, [rsp+48h+arg_8]
0x1800084e1  mov     rbx, [rsp+48h+arg_0]
0x1800084e6  jz      short loc_1800084FF
0x1800084e8  test    byte ptr [rcx+1Ch], 10h
0x1800084ec  jz      short loc_1800084FF
0x1800084ee  mov     rcx, [rcx+10h]
0x1800084f2  mov     edx, 2Ch ; ','
0x1800084f7  mov     r9d, edi
0x1800084fa  call    WPP_SF_D
0x1800084ff  mov     eax, edi
0x180008501  mov     rdi, [rsp+48h+var_8]
0x180008506  add     rsp, 48h
0x18000850a  retn
```
