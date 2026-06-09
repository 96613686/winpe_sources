# ServiceHandlerEx

- ea: `0x180002240`
- end: `0x180002477`
- name: `ServiceHandlerEx`
- size: `567`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002240`
- `0x1800025e0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000244d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000244d`
- `USER32!PostMessageW` at `0x180002464`
- `USER32!PostMessageW` at `0x180002464`

## pseudocode

```c
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)
{
  WPARAM v4; // rdi
  LPARAM v7; // r9
  WPARAM v8; // r8
  UINT v9; // edx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9

  v4 = dwEventType;
  switch ( dwControl )
  {
    case 1u:
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_39;
      }
      v11 = 14;
      v12 = 1;
      goto LABEL_38;
    case 2u:
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v14 = 13;
      v15 = 2;
LABEL_33:
      WPP_SF_D(v13[2], v14, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids, v15);
      return 0;
    case 3u:
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v14 = 12;
      v15 = 3;
      goto LABEL_33;
    case 4u:
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v14 = 11;
      v15 = 4;
      goto LABEL_33;
    case 5u:
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_39;
      }
      v11 = 15;
      v12 = 5;
LABEL_38:
      WPP_SF_D(v10[2], v11, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids, v12);
LABEL_39:
      if ( hService )
      {
        ServiceStatus.dwCurrentState = 3;
        SetServiceStatus(hService, &ServiceStatus);
      }
      v7 = 0;
      v8 = 0;
      v9 = 16;
      goto LABEL_42;
    case 0xEu:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids, 14);
      }
      v7 = lpEventData[1];
      v8 = v4;
      v9 = 689;
LABEL_42:
      PostMessageW(hWndHidServ, v9, v8, v7);
      return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids, dwControl);
  }
  return 120;
}

```

## disassembly

```asm
0x180002240  mov     [rsp+arg_0], rbx
0x180002245  push    rdi
0x180002246  sub     rsp, 20h
0x18000224a  mov     eax, ecx
0x18000224c  mov     edi, edx
0x18000224e  mov     rbx, r8
0x180002251  mov     r9d, ecx
0x180002254  sub     eax, 1
0x180002257  jz      loc_1800023F8
0x18000225d  sub     eax, 1
0x180002260  jz      loc_1800023B2
0x180002266  sub     eax, 1
0x180002269  jz      loc_18000237C
0x18000226f  sub     eax, 1
0x180002272  jz      loc_180002346
0x180002278  sub     eax, 1
0x18000227b  jz      loc_18000230D
0x180002281  cmp     eax, 9
0x180002284  jz      short loc_1800022C4
0x180002286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000228d  lea     rax, WPP_GLOBAL_Control
0x180002294  cmp     rcx, rax
0x180002297  jz      short loc_1800022BA
0x180002299  test    byte ptr [rcx+1Ch], 1
0x18000229d  jz      short loc_1800022BA
0x18000229f  cmp     byte ptr [rcx+19h], 3
0x1800022a3  jb      short loc_1800022BA
0x1800022a5  mov     rcx, [rcx+10h]
0x1800022a9  lea     r8, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids
0x1800022b0  mov     edx, 11h
0x1800022b5  call    WPP_SF_D
0x1800022ba  mov     eax, 78h ; 'x'
0x1800022bf  jmp     loc_18000246C
0x1800022c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022cb  lea     rax, WPP_GLOBAL_Control
0x1800022d2  cmp     rcx, rax
0x1800022d5  jz      short loc_1800022FC
0x1800022d7  test    byte ptr [rcx+1Ch], 1
0x1800022db  jz      short loc_1800022FC
0x1800022dd  cmp     byte ptr [rcx+19h], 4
0x1800022e1  jb      short loc_1800022FC
0x1800022e3  mov     rcx, [rcx+10h]
0x1800022e7  lea     r8, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids
0x1800022ee  mov     edx, 10h
0x1800022f3  lea     r9d, [rdx-2]
0x1800022f7  call    WPP_SF_D
0x1800022fc  mov     r9d, [rbx+4]
0x180002300  mov     r8, rdi
0x180002303  mov     edx, 2B1h
0x180002308  jmp     loc_18000245D
0x18000230d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002314  lea     rax, WPP_GLOBAL_Control
0x18000231b  cmp     rcx, rax
0x18000231e  jz      loc_180002430
0x180002324  test    byte ptr [rcx+1Ch], 1
0x180002328  jz      loc_180002430
0x18000232e  cmp     byte ptr [rcx+19h], 4
0x180002332  jb      loc_180002430
0x180002338  mov     edx, 0Fh
0x18000233d  lea     r9d, [rdx-0Ah]
0x180002341  jmp     loc_180002420
0x180002346  mov     rcx, cs:WPP_GLOBAL_Control
0x18000234d  lea     rax, WPP_GLOBAL_Control
0x180002354  cmp     rcx, rax
0x180002357  jz      loc_18000246A
0x18000235d  test    byte ptr [rcx+1Ch], 1
0x180002361  jz      loc_18000246A
0x180002367  cmp     byte ptr [rcx+19h], 4
0x18000236b  jb      loc_18000246A
0x180002371  mov     edx, 0Bh
0x180002376  lea     r9d, [rdx-7]
0x18000237a  jmp     short loc_1800023E6
0x18000237c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002383  lea     rax, WPP_GLOBAL_Control
0x18000238a  cmp     rcx, rax
0x18000238d  jz      loc_18000246A
0x180002393  test    byte ptr [rcx+1Ch], 1
0x180002397  jz      loc_18000246A
0x18000239d  cmp     byte ptr [rcx+19h], 4
0x1800023a1  jb      loc_18000246A
0x1800023a7  mov     edx, 0Ch
0x1800023ac  lea     r9d, [rdx-9]
0x1800023b0  jmp     short loc_1800023E6
0x1800023b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b9  lea     rax, WPP_GLOBAL_Control
0x1800023c0  cmp     rcx, rax
0x1800023c3  jz      loc_18000246A
0x1800023c9  test    byte ptr [rcx+1Ch], 1
0x1800023cd  jz      loc_18000246A
0x1800023d3  cmp     byte ptr [rcx+19h], 4
0x1800023d7  jb      loc_18000246A
0x1800023dd  mov     edx, 0Dh
0x1800023e2  lea     r9d, [rdx-0Bh]
0x1800023e6  mov     rcx, [rcx+10h]
0x1800023ea  lea     r8, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids
0x1800023f1  call    WPP_SF_D
0x1800023f6  jmp     short loc_18000246A
0x1800023f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023ff  lea     rax, WPP_GLOBAL_Control
0x180002406  cmp     rcx, rax
0x180002409  jz      short loc_180002430
0x18000240b  test    byte ptr [rcx+1Ch], 1
0x18000240f  jz      short loc_180002430
0x180002411  cmp     byte ptr [rcx+19h], 4
0x180002415  jb      short loc_180002430
0x180002417  mov     edx, 0Eh
0x18000241c  lea     r9d, [rdx-0Dh]
0x180002420  mov     rcx, [rcx+10h]
0x180002424  lea     r8, WPP_18942586ea5b38f27ded2405828f1ea0_Traceguids
0x18000242b  call    WPP_SF_D
0x180002430  mov     rcx, cs:hService; hServiceStatus
0x180002437  test    rcx, rcx
0x18000243a  jz      short loc_180002453
0x18000243c  lea     rdx, ServiceStatus; lpServiceStatus
0x180002443  mov     cs:ServiceStatus.dwCurrentState, 3
0x18000244d  call    cs:__imp_SetServiceStatus
0x180002453  xor     r9d, r9d; lParam
0x180002456  xor     r8d, r8d; wParam
0x180002459  lea     edx, [r9+10h]; Msg
0x18000245d  mov     rcx, cs:hWndHidServ; hWnd
0x180002464  call    cs:__imp_PostMessageW
0x18000246a  xor     eax, eax
0x18000246c  mov     rbx, [rsp+28h+arg_0]
0x180002471  add     rsp, 20h
0x180002475  pop     rdi
0x180002476  retn
```
