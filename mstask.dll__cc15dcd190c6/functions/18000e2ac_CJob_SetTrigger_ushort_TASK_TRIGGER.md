# CJob::SetTrigger(ushort,_TASK_TRIGGER *)

- ea: `0x18000e2ac`
- end: `0x18000e49e`
- name: `?SetTrigger@CJob@@QEAAJGPEAU_TASK_TRIGGER@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16, struct _TASK_TRIGGER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000e550`

## callees

- `0x180007640`
- `0x1800085d8`
- `0x18000d470`
- `0x18000e2ac`
- `0x1800194ec`

## pseudocode

```c
__int64 __fastcall CJob::SetTrigger(CJob *this, unsigned __int16 a2, struct _TASK_TRIGGER *a3)
{
  struct _TASK_TRIGGER *Trigger; // rdi
  int v7; // edx
  DWORD MinutesDuration; // eax
  DWORD *p_MinutesInterval; // r8
  TASK_TRIGGER_TYPE TriggerType; // ecx
  __int32 v11; // ecx
  __int32 v12; // ecx
  __int32 v13; // ecx
  int v14; // ecx
  int v15; // ecx
  WORD v16; // cx
  WORD v17; // cx
  WORD DaysInterval; // ax
  DWORD v19; // eax

  Trigger = CJob::_GetTrigger(this, a2);
  if ( !Trigger )
    return 2147500037LL;
  if ( a3->cbTriggerSize != 48
    || a3->wStartHour > 0x17u
    || a3->wStartMinute > 0x3Bu
    || !(unsigned int)IsValidDate(a3->wBeginMonth, a3->wBeginDay, a3->wBeginYear)
    || (a3->rgFlags & 1) != 0 && !(unsigned int)IsValidDate(a3->wEndMonth, a3->wEndDay, a3->wEndYear) )
  {
    return 2147942487LL;
  }
  MinutesDuration = a3->MinutesDuration;
  p_MinutesInterval = &a3->MinutesInterval;
  if ( (MinutesDuration || *p_MinutesInterval) && *p_MinutesInterval >= MinutesDuration )
    return 2147942487LL;
  TriggerType = a3->TriggerType;
  if ( TriggerType == TASK_TIME_TRIGGER_ONCE )
    goto LABEL_32;
  v11 = TriggerType - 1;
  if ( !v11 )
  {
    DaysInterval = a3->Type.Daily.DaysInterval;
    if ( DaysInterval )
    {
      Trigger->Type.Daily.DaysInterval = DaysInterval;
      goto LABEL_32;
    }
    return 2147942487LL;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v17 = a3->Type.Daily.DaysInterval;
    if ( !v17 || (unsigned __int16)(a3->Type.Weekly.rgfDaysOfTheWeek - 1) > 0x7Eu )
      return 2147942487LL;
    Trigger->Type.Daily.DaysInterval = v17;
    Trigger->Type.Weekly.rgfDaysOfTheWeek = a3->Type.Weekly.rgfDaysOfTheWeek;
    goto LABEL_32;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    if ( (unsigned int)IsValidMonthlyDateTrigger(a3) )
    {
      Trigger->Type.MonthlyDate.rgfDays = a3->Type.MonthlyDate.rgfDays;
LABEL_26:
      Trigger->Type.MonthlyDate.rgfMonths = a3->Type.MonthlyDate.rgfMonths;
      goto LABEL_32;
    }
    return 2147942487LL;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v16 = a3->Type.Daily.DaysInterval;
    if ( (unsigned __int16)(v16 - 1) > 4u )
      return 2147942487LL;
    if ( (unsigned __int16)(a3->Type.Weekly.rgfDaysOfTheWeek - 1) > 0x7Eu )
      return 2147942487LL;
    v7 = 4094;
    if ( (unsigned __int16)(a3->Type.MonthlyDate.rgfMonths - 1) > 0xFFEu )
      return 2147942487LL;
    Trigger->Type.Daily.DaysInterval = v16;
    Trigger->Type.Weekly.rgfDaysOfTheWeek = a3->Type.Weekly.rgfDaysOfTheWeek;
    goto LABEL_26;
  }
  v15 = v14 - 1;
  if ( v15 && (unsigned int)(v15 - 1) >= 2 )
    return 2147942487LL;
LABEL_32:
  Trigger->TriggerType = a3->TriggerType;
  Trigger->cbTriggerSize = a3->cbTriggerSize;
  Trigger->wBeginYear = a3->wBeginYear;
  Trigger->wBeginMonth = a3->wBeginMonth;
  Trigger->wBeginDay = a3->wBeginDay;
  Trigger->wEndYear = a3->wEndYear;
  Trigger->wEndMonth = a3->wEndMonth;
  Trigger->wEndDay = a3->wEndDay;
  Trigger->wStartHour = a3->wStartHour;
  Trigger->wStartMinute = a3->wStartMinute;
  Trigger->MinutesDuration = a3->MinutesDuration;
  v19 = *p_MinutesInterval;
  Trigger->rgFlags &= 0xFFFF8000;
  Trigger->MinutesInterval = v19;
  Trigger->rgFlags = a3->rgFlags & 0x7FFF;
  *((_DWORD *)this + 22) = *((_DWORD *)this + 22) & 0x4F3FFFFF | 0x90800000;
  CJob::UpdateJobState(this, v7);
  return 0;
}

```

## disassembly

```asm
0x18000e2ac  push    rbx
0x18000e2ae  push    rbp
0x18000e2af  push    rsi
0x18000e2b0  push    rdi
0x18000e2b1  sub     rsp, 28h
0x18000e2b5  mov     rbx, r8
0x18000e2b8  mov     rsi, rcx
0x18000e2bb  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x18000e2c0  xor     ebp, ebp
0x18000e2c2  mov     rdi, rax
0x18000e2c5  test    rax, rax
0x18000e2c8  jnz     short loc_18000E2D4
0x18000e2ca  mov     eax, 80004005h
0x18000e2cf  jmp     loc_18000E382
0x18000e2d4  cmp     word ptr [rbx], 30h ; '0'
0x18000e2d8  jnz     loc_18000E37D
0x18000e2de  cmp     word ptr [rbx+10h], 17h
0x18000e2e3  ja      loc_18000E37D
0x18000e2e9  cmp     word ptr [rbx+12h], 3Bh ; ';'
0x18000e2ee  ja      loc_18000E37D
0x18000e2f4  movzx   r8d, word ptr [rbx+4]; unsigned __int16
0x18000e2f9  movzx   edx, word ptr [rbx+8]; unsigned __int16
0x18000e2fd  movzx   ecx, word ptr [rbx+6]; unsigned __int16
0x18000e301  call    ?IsValidDate@@YAHGGG@Z; IsValidDate(ushort,ushort,ushort)
0x18000e306  test    eax, eax
0x18000e308  jz      short loc_18000E37D
0x18000e30a  test    byte ptr [rbx+1Ch], 1
0x18000e30e  jz      short loc_18000E326
0x18000e310  movzx   r8d, word ptr [rbx+0Ah]; unsigned __int16
0x18000e315  movzx   edx, word ptr [rbx+0Eh]; unsigned __int16
0x18000e319  movzx   ecx, word ptr [rbx+0Ch]; unsigned __int16
0x18000e31d  call    ?IsValidDate@@YAHGGG@Z; IsValidDate(ushort,ushort,ushort)
0x18000e322  test    eax, eax
0x18000e324  jz      short loc_18000E37D
0x18000e326  mov     eax, [rbx+14h]
0x18000e329  lea     r8, [rbx+18h]
0x18000e32d  test    eax, eax
0x18000e32f  jnz     short loc_18000E336
0x18000e331  cmp     [r8], ebp
0x18000e334  jbe     short loc_18000E33B
0x18000e336  cmp     [r8], eax
0x18000e339  jnb     short loc_18000E37D
0x18000e33b  mov     ecx, [rbx+20h]
0x18000e33e  test    ecx, ecx
0x18000e340  jz      loc_18000E415
0x18000e346  sub     ecx, 1
0x18000e349  jz      loc_18000E404
0x18000e34f  sub     ecx, 1
0x18000e352  jz      loc_18000E3E0
0x18000e358  sub     ecx, 1
0x18000e35b  jz      short loc_18000E3C4
0x18000e35d  sub     ecx, 1
0x18000e360  jz      short loc_18000E38B
0x18000e362  sub     ecx, 1
0x18000e365  jz      loc_18000E415
0x18000e36b  sub     ecx, 1
0x18000e36e  jz      loc_18000E415
0x18000e374  cmp     ecx, 1
0x18000e377  jz      loc_18000E415
0x18000e37d  mov     eax, 80070057h
0x18000e382  add     rsp, 28h
0x18000e386  pop     rdi
0x18000e387  pop     rsi
0x18000e388  pop     rbp
0x18000e389  pop     rbx
0x18000e38a  retn
0x18000e38b  movzx   ecx, word ptr [rbx+24h]
0x18000e38f  lea     eax, [rcx-1]
0x18000e392  cmp     ax, 4
0x18000e396  ja      short loc_18000E37D
0x18000e398  movzx   eax, word ptr [rbx+26h]
0x18000e39c  dec     ax
0x18000e39f  cmp     ax, 7Eh ; '~'
0x18000e3a3  ja      short loc_18000E37D
0x18000e3a5  movzx   eax, word ptr [rbx+28h]
0x18000e3a9  mov     edx, 0FFEh
0x18000e3ae  dec     ax
0x18000e3b1  cmp     ax, dx
0x18000e3b4  ja      short loc_18000E37D
0x18000e3b6  mov     [rdi+24h], cx
0x18000e3ba  movzx   eax, word ptr [rbx+26h]
0x18000e3be  mov     [rdi+26h], ax
0x18000e3c2  jmp     short loc_18000E3D6
0x18000e3c4  mov     rcx, rbx; struct _TASK_TRIGGER *
0x18000e3c7  call    ?IsValidMonthlyDateTrigger@@YAHPEAU_TASK_TRIGGER@@@Z; IsValidMonthlyDateTrigger(_TASK_TRIGGER *)
0x18000e3cc  test    eax, eax
0x18000e3ce  jz      short loc_18000E37D
0x18000e3d0  mov     eax, [rbx+24h]
0x18000e3d3  mov     [rdi+24h], eax
0x18000e3d6  movzx   eax, word ptr [rbx+28h]
0x18000e3da  mov     [rdi+28h], ax
0x18000e3de  jmp     short loc_18000E415
0x18000e3e0  movzx   ecx, word ptr [rbx+24h]
0x18000e3e4  test    cx, cx
0x18000e3e7  jz      short loc_18000E37D
0x18000e3e9  movzx   eax, word ptr [rbx+26h]
0x18000e3ed  dec     ax
0x18000e3f0  cmp     ax, 7Eh ; '~'
0x18000e3f4  ja      short loc_18000E37D
0x18000e3f6  mov     [rdi+24h], cx
0x18000e3fa  movzx   eax, word ptr [rbx+26h]
0x18000e3fe  mov     [rdi+26h], ax
0x18000e402  jmp     short loc_18000E415
0x18000e404  movzx   eax, word ptr [rbx+24h]
0x18000e408  test    ax, ax
0x18000e40b  jz      loc_18000E37D
0x18000e411  mov     [rdi+24h], ax
0x18000e415  mov     eax, [rbx+20h]
0x18000e418  mov     rcx, rsi; this
0x18000e41b  mov     [rdi+20h], eax
0x18000e41e  movzx   eax, word ptr [rbx]
0x18000e421  mov     [rdi], ax
0x18000e424  movzx   eax, word ptr [rbx+4]
0x18000e428  mov     [rdi+4], ax
0x18000e42c  movzx   eax, word ptr [rbx+6]
0x18000e430  mov     [rdi+6], ax
0x18000e434  movzx   eax, word ptr [rbx+8]
0x18000e438  mov     [rdi+8], ax
0x18000e43c  movzx   eax, word ptr [rbx+0Ah]
0x18000e440  mov     [rdi+0Ah], ax
0x18000e444  movzx   eax, word ptr [rbx+0Ch]
0x18000e448  mov     [rdi+0Ch], ax
0x18000e44c  movzx   eax, word ptr [rbx+0Eh]
0x18000e450  mov     [rdi+0Eh], ax
0x18000e454  movzx   eax, word ptr [rbx+10h]
0x18000e458  mov     [rdi+10h], ax
0x18000e45c  movzx   eax, word ptr [rbx+12h]
0x18000e460  mov     [rdi+12h], ax
0x18000e464  mov     eax, [rbx+14h]
0x18000e467  mov     [rdi+14h], eax
0x18000e46a  mov     eax, [r8]
0x18000e46d  and     dword ptr [rdi+1Ch], 0FFFF8000h
0x18000e474  mov     [rdi+18h], eax
0x18000e477  mov     eax, [rbx+1Ch]
0x18000e47a  and     eax, 7FFFh
0x18000e47f  mov     [rdi+1Ch], eax
0x18000e482  mov     eax, [rsi+58h]
0x18000e485  and     eax, 0DFBFFFFFh
0x18000e48a  or      eax, 90800000h
0x18000e48f  mov     [rsi+58h], eax
0x18000e492  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x18000e497  xor     eax, eax
0x18000e499  jmp     loc_18000E382
```
