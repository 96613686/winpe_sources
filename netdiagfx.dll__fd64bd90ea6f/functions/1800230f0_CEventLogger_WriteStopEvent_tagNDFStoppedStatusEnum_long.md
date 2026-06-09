# CEventLogger::WriteStopEvent(tagNDFStoppedStatusEnum,long)

- ea: `0x1800230f0`
- end: `0x1800231fa`
- name: `?WriteStopEvent@CEventLogger@@UEAAJW4tagNDFStoppedStatusEnum@@J@Z`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800230f0`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1800231cb`
- `ADVAPI32!EventWrite` at `0x1800231cb`
- `ADVAPI32!EventEnabled` at `0x1800231ac`
- `ADVAPI32!EventEnabled` at `0x1800231ac`

## pseudocode

```c
__int64 __fastcall CEventLogger::WriteStopEvent(__int64 a1, int a2, int a3)
{
  unsigned int v3; // edi
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  __int64 *v9; // rbx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  signed int v14; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF
  int v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = a3;
  v3 = 0;
  if ( a2 > 7 )
  {
    v10 = a2 - 8;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( !v13 )
          {
LABEL_19:
            v9 = NDFStopSuccessRepairEvtDesc;
            goto LABEL_21;
          }
          if ( (unsigned int)(v13 - 2) > 1 )
            return v3;
        }
LABEL_18:
        v9 = NDFStopSuccessDiagEvtDesc;
        goto LABEL_21;
      }
    }
LABEL_20:
    v9 = NDFStopCancelRepairEvtDesc;
    goto LABEL_21;
  }
  if ( a2 == 7 )
    goto LABEL_20;
  if ( !a2 )
  {
    v9 = NDFStopFailDiagEvtDesc;
    goto LABEL_21;
  }
  v4 = a2 - 1;
  if ( !v4 || (v5 = v4 - 1) == 0 )
  {
    v9 = NDFStopFailRepairEvtDesc;
    goto LABEL_21;
  }
  v6 = v5 - 1;
  if ( !v6 )
    goto LABEL_18;
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_19;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_19;
  if ( v8 != 1 )
    return v3;
  v9 = (__int64 *)&NDFStopCancelDiagEvtDesc;
LABEL_21:
  UserData.Ptr = (ULONGLONG)&v17;
  *(_QWORD *)&UserData.Size = 4;
  if ( EventEnabled(NETDIAG_EVT_GUID_Context, (PCEVENT_DESCRIPTOR)v9) )
  {
    v14 = EventWrite(NETDIAG_EVT_GUID_Context, (PCEVENT_DESCRIPTOR)v9, 1u, &UserData);
    v3 = v14;
    if ( v14 > 0 )
      return (unsigned __int16)v14 | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x1800230f0  mov     [rsp+arg_0], rbx
0x1800230f5  mov     [rsp+arg_10], r8d
0x1800230fa  push    rdi
0x1800230fb  sub     rsp, 40h
0x1800230ff  mov     rax, cs:__security_cookie
0x180023106  xor     rax, rsp
0x180023109  mov     [rsp+48h+var_18], rax
0x18002310e  xor     edi, edi
0x180023110  cmp     edx, 7
0x180023113  jg      short loc_180023158
0x180023115  jz      short loc_180023188
0x180023117  test    edx, edx
0x180023119  jz      short loc_18002314F
0x18002311b  sub     edx, 1
0x18002311e  jz      short loc_180023146
0x180023120  sub     edx, 1
0x180023123  jz      short loc_180023146
0x180023125  sub     edx, 1
0x180023128  jz      short loc_180023176
0x18002312a  sub     edx, 1
0x18002312d  jz      short loc_18002317F
0x18002312f  sub     edx, 1
0x180023132  jz      short loc_18002317F
0x180023134  cmp     edx, 1
0x180023137  jnz     loc_1800231E0
0x18002313d  lea     rbx, NDFStopCancelDiagEvtDesc
0x180023144  jmp     short loc_18002318F
0x180023146  lea     rbx, NDFStopFailRepairEvtDesc
0x18002314d  jmp     short loc_18002318F
0x18002314f  lea     rbx, NDFStopFailDiagEvtDesc
0x180023156  jmp     short loc_18002318F
0x180023158  sub     edx, 8
0x18002315b  jz      short loc_180023188
0x18002315d  sub     edx, 1
0x180023160  jz      short loc_180023188
0x180023162  sub     edx, 1
0x180023165  jz      short loc_180023176
0x180023167  sub     edx, 1
0x18002316a  jz      short loc_18002317F
0x18002316c  sub     edx, 2
0x18002316f  jz      short loc_180023176
0x180023171  cmp     edx, 1
0x180023174  jnz     short loc_1800231E0
0x180023176  lea     rbx, NDFStopSuccessDiagEvtDesc
0x18002317d  jmp     short loc_18002318F
0x18002317f  lea     rbx, NDFStopSuccessRepairEvtDesc
0x180023186  jmp     short loc_18002318F
0x180023188  lea     rbx, NDFStopCancelRepairEvtDesc
0x18002318f  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180023196  lea     rax, [rsp+48h+arg_10]
0x18002319b  mov     rdx, rbx; EventDescriptor
0x18002319e  mov     [rsp+48h+UserData.Ptr], rax
0x1800231a3  mov     qword ptr [rsp+48h+UserData.Size], 4
0x1800231ac  call    cs:__imp_EventEnabled
0x1800231b2  test    al, al
0x1800231b4  jz      short loc_1800231E0
0x1800231b6  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x1800231bd  lea     r9, [rsp+48h+UserData]; UserData
0x1800231c2  mov     r8d, 1; UserDataCount
0x1800231c8  mov     rdx, rbx; EventDescriptor
0x1800231cb  call    cs:__imp_EventWrite
0x1800231d1  mov     edi, eax
0x1800231d3  test    eax, eax
0x1800231d5  jle     short loc_1800231E0
0x1800231d7  movzx   edi, ax
0x1800231da  or      edi, 80070000h
0x1800231e0  mov     eax, edi
0x1800231e2  mov     rcx, [rsp+48h+var_18]
0x1800231e7  xor     rcx, rsp; StackCookie
0x1800231ea  call    __security_check_cookie
0x1800231ef  mov     rbx, [rsp+48h+arg_0]
0x1800231f4  add     rsp, 40h
0x1800231f8  pop     rdi
0x1800231f9  retn
```
