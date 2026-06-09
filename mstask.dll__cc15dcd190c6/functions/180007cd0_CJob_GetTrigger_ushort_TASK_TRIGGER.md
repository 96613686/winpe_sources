# CJob::GetTrigger(ushort,_TASK_TRIGGER *)

- ea: `0x180007cd0`
- end: `0x180007e54`
- name: `?GetTrigger@CJob@@QEAAJGPEAU_TASK_TRIGGER@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16, struct _TASK_TRIGGER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e4f0`

## callees

- `0x180007cd0`

## pseudocode

```c
__int64 __fastcall CJob::GetTrigger(CJob *this, __int16 a2, struct _TASK_TRIGGER *a3)
{
  unsigned __int16 i; // ax
  __int64 v5; // r8
  int v6; // eax
  __int64 result; // rax
  DWORD v8; // edx
  DWORD v9; // ecx

  for ( i = 0; ; ++i )
  {
    if ( i >= *((_WORD *)this + 16) )
      return 2147500037LL;
    v5 = *((_QWORD *)this + 3) + 48LL * i;
    if ( *(_WORD *)(v5 + 2) == a2 )
      break;
  }
  if ( !v5 )
    return 2147500037LL;
  v6 = *(_DWORD *)(v5 + 32);
  if ( v6 == 1 )
  {
    a3->Type.Daily.DaysInterval = *(_WORD *)(v5 + 36);
LABEL_13:
    a3->TriggerType = *(_DWORD *)(v5 + 32);
    a3->cbTriggerSize = *(_WORD *)v5;
    a3->wBeginYear = *(_WORD *)(v5 + 4);
    a3->wBeginMonth = *(_WORD *)(v5 + 6);
    a3->wBeginDay = *(_WORD *)(v5 + 8);
    a3->wEndYear = *(_WORD *)(v5 + 10);
    a3->wEndMonth = *(_WORD *)(v5 + 12);
    a3->wEndDay = *(_WORD *)(v5 + 14);
    a3->wStartHour = *(_WORD *)(v5 + 16);
    a3->wStartMinute = *(_WORD *)(v5 + 18);
    a3->MinutesDuration = *(_DWORD *)(v5 + 20);
    a3->MinutesInterval = *(_DWORD *)(v5 + 24);
    v8 = *(_DWORD *)(v5 + 28);
    a3->Reserved1 = 0;
    v9 = v8 & 0x7FFF;
    a3->rgFlags = v8;
    a3->Reserved2 = *(_WORD *)(v5 + 44);
    a3->wRandomMinutesInterval = *(_WORD *)(v5 + 46);
    if ( (v8 & 0x10000) != 0 )
      v9 |= 4u;
    result = 0;
    a3->rgFlags = v9;
  }
  else
  {
    switch ( v6 )
    {
      case 0:
      case 5:
      case 6:
      case 7:
        goto LABEL_13;
      case 2:
        a3->Type.Daily.DaysInterval = *(_WORD *)(v5 + 36);
        a3->Type.Weekly.rgfDaysOfTheWeek = *(_WORD *)(v5 + 38);
        goto LABEL_13;
      case 3:
        a3->Type.MonthlyDate.rgfDays = *(_DWORD *)(v5 + 36);
        a3->Type.MonthlyDate.rgfMonths = *(_WORD *)(v5 + 40);
        goto LABEL_13;
      case 4:
        a3->Type.Daily.DaysInterval = *(_WORD *)(v5 + 36);
        a3->Type.Weekly.rgfDaysOfTheWeek = *(_WORD *)(v5 + 38);
        a3->Type.MonthlyDate.rgfMonths = *(_WORD *)(v5 + 40);
        goto LABEL_13;
      default:
        result = 2147942487LL;
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007cd0  mov     [rsp+arg_0], rbx
0x180007cd5  movzx   r9d, word ptr [rcx+20h]
0x180007cda  mov     rbx, r8
0x180007cdd  xor     eax, eax
0x180007cdf  nop
0x180007ce0  cmp     ax, r9w
0x180007ce4  jnb     loc_180007E28
0x180007cea  movzx   r8d, ax
0x180007cee  lea     r8, [r8+r8*2]
0x180007cf2  shl     r8, 4
0x180007cf6  add     r8, [rcx+18h]
0x180007cfa  cmp     [r8+2], dx
0x180007cff  jz      short loc_180007D06
0x180007d01  inc     ax
0x180007d04  jmp     short loc_180007CE0
0x180007d06  test    r8, r8
0x180007d09  jz      loc_180007E28
0x180007d0f  movsxd  rax, dword ptr [r8+20h]
0x180007d13  cmp     eax, 1
0x180007d16  jz      short loc_180007D7D
0x180007d18  cmp     eax, 7; switch 8 cases
0x180007d1b  ja      short def_180007D2E; jumptable 0000000180007D2E default case, case 1
0x180007d1d  lea     rdx, __ImageBase
0x180007d24  mov     ecx, ds:(jpt_180007D2E - 180000000h)[rdx+rax*4]
0x180007d2b  add     rcx, rdx
0x180007d2e  jmp     rcx; switch jump
0x180007d30  movzx   eax, word ptr [r8+24h]; jumptable 0000000180007D2E case 2
0x180007d35  mov     [rbx+24h], ax
0x180007d39  movzx   eax, word ptr [r8+26h]
0x180007d3e  mov     [rbx+26h], ax
0x180007d42  jmp     short loc_180007D86; jumptable 0000000180007D2E cases 0,5-7
0x180007d44  mov     eax, [r8+24h]; jumptable 0000000180007D2E case 3
0x180007d48  mov     [rbx+24h], eax
0x180007d4b  movzx   eax, word ptr [r8+28h]
0x180007d50  mov     [rbx+28h], ax
0x180007d54  jmp     short loc_180007D86; jumptable 0000000180007D2E cases 0,5-7
0x180007d56  movzx   eax, word ptr [r8+24h]; jumptable 0000000180007D2E case 4
0x180007d5b  mov     [rbx+24h], ax
0x180007d5f  movzx   eax, word ptr [r8+26h]
0x180007d64  mov     [rbx+26h], ax
0x180007d68  movzx   eax, word ptr [r8+28h]
0x180007d6d  mov     [rbx+28h], ax
0x180007d71  jmp     short loc_180007D86; jumptable 0000000180007D2E cases 0,5-7
0x180007d73  mov     eax, 80070057h; jumptable 0000000180007D2E default case, case 1
0x180007d78  jmp     loc_180007E2D
0x180007d7d  movzx   eax, word ptr [r8+24h]
0x180007d82  mov     [rbx+24h], ax
0x180007d86  mov     eax, [r8+20h]; jumptable 0000000180007D2E cases 0,5-7
0x180007d8a  mov     [rbx+20h], eax
0x180007d8d  movzx   eax, word ptr [r8]
0x180007d91  mov     [rbx], ax
0x180007d94  movzx   eax, word ptr [r8+4]
0x180007d99  mov     [rbx+4], ax
0x180007d9d  movzx   eax, word ptr [r8+6]
0x180007da2  mov     [rbx+6], ax
0x180007da6  movzx   eax, word ptr [r8+8]
0x180007dab  mov     [rbx+8], ax
0x180007daf  movzx   eax, word ptr [r8+0Ah]
0x180007db4  mov     [rbx+0Ah], ax
0x180007db8  movzx   eax, word ptr [r8+0Ch]
0x180007dbd  mov     [rbx+0Ch], ax
0x180007dc1  movzx   eax, word ptr [r8+0Eh]
0x180007dc6  mov     [rbx+0Eh], ax
0x180007dca  movzx   eax, word ptr [r8+10h]
0x180007dcf  mov     [rbx+10h], ax
0x180007dd3  movzx   eax, word ptr [r8+12h]
0x180007dd8  mov     [rbx+12h], ax
0x180007ddc  mov     eax, [r8+14h]
0x180007de0  mov     [rbx+14h], eax
0x180007de3  mov     eax, [r8+18h]
0x180007de7  mov     [rbx+18h], eax
0x180007dea  xor     eax, eax
0x180007dec  mov     edx, [r8+1Ch]
0x180007df0  mov     ecx, edx
0x180007df2  mov     [rbx+2], ax
0x180007df6  and     ecx, 7FFFh
0x180007dfc  mov     [rbx+1Ch], edx
0x180007dff  movzx   eax, word ptr [r8+2Ch]
0x180007e04  mov     [rbx+2Ch], ax
0x180007e08  movzx   eax, word ptr [r8+2Eh]
0x180007e0d  mov     [rbx+2Eh], ax
0x180007e11  mov     eax, ecx
0x180007e13  or      eax, 4
0x180007e16  bt      edx, 10h
0x180007e1a  cmovb   ecx, eax
0x180007e1d  xor     eax, eax
0x180007e1f  mov     [rbx+1Ch], ecx
0x180007e22  mov     rbx, [rsp+arg_0]
0x180007e27  retn
0x180007e28  mov     eax, 80004005h
0x180007e2d  mov     rbx, [rsp+arg_0]
0x180007e32  retn
```
