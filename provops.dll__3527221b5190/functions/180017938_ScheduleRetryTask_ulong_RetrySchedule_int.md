# ScheduleRetryTask(ulong,RetrySchedule &,int)

- ea: `0x180017938`
- end: `0x180017a3d`
- name: `?ScheduleRetryTask@@YAJKAEAVRetrySchedule@@H@Z`
- size: `261`
- prototype: `__int64 __fastcall(int, struct RetrySchedule *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180013e9c`

## callees

- `0x180017938`
- `0x18001b388`
- `0x180027208`
- `0x1800276a4`

## string_xrefs

- `0x180017956`: `ProvRetryTask`

## pseudocode

```c
__int64 __fastcall ScheduleRetryTask(int a1, struct RetrySchedule *a2, int a3)
{
  unsigned __int64 v3; // rax
  __int64 *v4; // rdx
  __int64 v5; // r8
  __int64 *i; // rax
  __int64 *v7; // rcx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v11[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h]
  const wchar_t *v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    *(_QWORD *)v11 = L"ProvNonRebootRetry";
    v12 = 5;
    v13 = L"ProvRetryTask";
    if ( a3 )
      goto LABEL_19;
    v3 = *((_QWORD *)a2 + 1);
    if ( v3 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\retryschedule.cpp",
        v3 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        v11[0]);
    if ( a1 == (unsigned int)*((_QWORD *)a2 + 1) + 1 )
    {
LABEL_19:
      EnableTask(L"Retry");
    }
    else
    {
      v4 = **(__int64 ***)a2;
      v5 = (unsigned int)(a1 - 1);
      if ( a1 != 1 )
      {
        do
        {
          if ( !*((_BYTE *)v4 + 25) )
          {
            i = (__int64 *)v4[2];
            if ( *((_BYTE *)i + 25) )
            {
              for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                v4 = i;
            }
            else
            {
              v7 = (__int64 *)*i;
              if ( !*(_BYTE *)(*i + 25) )
              {
                do
                {
                  v4 = v7;
                  v7 = (__int64 *)*v7;
                }
                while ( !*((_BYTE *)v7 + 25) );
                goto LABEL_17;
              }
            }
            v4 = i;
          }
LABEL_17:
          --v5;
        }
        while ( v5 );
      }
      SetDelayedTask((const struct ProvTask *)v11, *((_DWORD *)v4 + 16));
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x6D, v8, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180017938  push    rbx
0x18001793a  sub     rsp, 40h
0x18001793e  mov     r9d, ecx
0x180017941  lea     rax, aProvnonrebootr; "ProvNonRebootRetry"
0x180017948  mov     qword ptr [rsp+48h+var_28], rax; int
0x18001794d  mov     [rsp+48h+var_20], 5
0x180017956  lea     rax, aProvretrytask; "ProvRetryTask"
0x18001795d  mov     [rsp+48h+var_18], rax
0x180017962  xor     r11d, r11d
0x180017965  test    r8d, r8d
0x180017968  jnz     loc_180017A0F
0x18001796e  mov     rax, [rdx+8]
0x180017972  mov     ebx, 0FFFFFFFFh
0x180017977  cmp     rax, rbx
0x18001797a  mov     ecx, eax
0x18001797c  jbe     short loc_180017980
0x18001797e  mov     ecx, ebx
0x180017980  cmp     rbx, rax
0x180017983  sbb     r8d, r8d
0x180017986  and     r8d, 80070216h
0x18001798d  mov     r10, [rsp+48h]
0x180017992  cmp     rax, rbx
0x180017995  ja      loc_180017A24
0x18001799b  lea     eax, [rcx+1]
0x18001799e  cmp     r9d, eax
0x1800179a1  jz      short loc_180017A0F
0x1800179a3  mov     rdx, [rdx]
0x1800179a6  mov     rdx, [rdx]
0x1800179a9  lea     eax, [r9-1]
0x1800179ad  mov     r8d, eax
0x1800179b0  test    eax, eax
0x1800179b2  jz      short loc_180017A00
0x1800179b4  cmp     [rdx+19h], r11b
0x1800179b8  jnz     short loc_1800179FA
0x1800179ba  mov     rax, [rdx+10h]
0x1800179be  cmp     [rax+19h], r11b
0x1800179c2  jnz     short loc_1800179DE
0x1800179c4  mov     rcx, [rax]
0x1800179c7  cmp     [rcx+19h], r11b
0x1800179cb  jnz     short loc_1800179F7
0x1800179cd  mov     rdx, rcx
0x1800179d0  mov     rax, [rcx]
0x1800179d3  mov     rcx, rax
0x1800179d6  cmp     [rax+19h], r11b
0x1800179da  jz      short loc_1800179CD
0x1800179dc  jmp     short loc_1800179FA
0x1800179de  mov     rax, [rdx+8]
0x1800179e2  jmp     short loc_1800179F1
0x1800179e4  cmp     rdx, [rax+10h]
0x1800179e8  jnz     short loc_1800179F7
0x1800179ea  mov     rdx, rax
0x1800179ed  mov     rax, [rax+8]
0x1800179f1  cmp     [rax+19h], r11b
0x1800179f5  jz      short loc_1800179E4
0x1800179f7  mov     rdx, rax
0x1800179fa  sub     r8, 1
0x1800179fe  jnz     short loc_1800179B4
0x180017a00  mov     edx, [rdx+40h]; unsigned int
0x180017a03  lea     rcx, [rsp+48h+var_28]; struct ProvTask *
0x180017a08  call    ?SetDelayedTask@@YAXAEBUProvTask@@K@Z; SetDelayedTask(ProvTask const &,ulong)
0x180017a0d  jmp     short loc_180017A1C
0x180017a0f  lea     rcx, aRetry; "Retry"
0x180017a16  call    ?EnableTask@@YAXPEBG@Z; EnableTask(ushort const *)
0x180017a1b  nop
0x180017a1c  xor     eax, eax
0x180017a1e  add     rsp, 40h
0x180017a22  pop     rbx
0x180017a23  retn
0x180017a24  mov     r9d, r8d; char *
0x180017a27  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\lib\\retrysche"...
0x180017a2e  mov     edx, 2Ch ; ','; void *
0x180017a33  mov     rcx, r10; this
0x180017a36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
