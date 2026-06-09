# FinishClaimingKey(bool,_PregenParms const *,DelayRetryAction *,bool,PregenTaskType,bool *)

- ea: `0x18001b950`
- end: `0x18001ba24`
- name: `?FinishClaimingKey@@YAX_NPEBU_PregenParms@@PEAW4DelayRetryAction@@0W4PregenTaskType@@PEA_N@Z`
- size: `212`
- prototype: `void __fastcall(char, __int64, enum DelayRetryAction *, char, unsigned int, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aa6c`

## callees

- `0x18001069c`
- `0x18001b950`
- `0x18001bbdc`
- `0x18001c760`
- `0x18001d2e0`
- `0x18001d764`

## string_xrefs

- `0x18001b983`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b9b2`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001b9fd`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FinishClaimingKey(char a1, __int64 a2, enum DelayRetryAction *a3, char a4, unsigned int a5, _BYTE *a6)
{
  int v9; // eax
  int AikEnrollRetryType; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1 )
  {
    if ( !*(_DWORD *)(a2 + 8) )
    {
      v9 = SetMinimumKeyCount((const struct _PregenParms *)a2);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v9,
          v13);
    }
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( a3 )
      {
        AikEnrollRetryType = GetAikEnrollRetryType(a3);
        if ( AikEnrollRetryType < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x113,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
            (const char *)(unsigned int)AikEnrollRetryType,
            v13);
      }
    }
  }
  if ( a4 && a5 )
  {
    if ( a5 == 3 )
    {
      v11 = ChangeKeyPregenTaskTriggersStatus(1);
      if ( v11 < 0 )
      {
        v12 = 297;
        goto LABEL_16;
      }
    }
    else
    {
      v11 = NgcTriggerTask(a5);
      if ( v11 < 0 )
      {
        v12 = 290;
LABEL_16:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
          (const char *)(unsigned int)v11,
          v13);
      }
    }
    *a6 = 1;
  }
}

```

## disassembly

```asm
0x18001b950  mov     [rsp+arg_0], rbx
0x18001b955  mov     [rsp+arg_8], rsi
0x18001b95a  push    rdi; int
0x18001b95b  sub     rsp, 20h
0x18001b95f  mov     sil, r9b
0x18001b962  mov     rdi, r8
0x18001b965  mov     rbx, rdx
0x18001b968  test    cl, cl
0x18001b96a  jz      short loc_18001B9C6
0x18001b96c  cmp     dword ptr [rdx+8], 0
0x18001b970  jnz     short loc_18001B997
0x18001b972  mov     rcx, rdx; struct _PregenParms *
0x18001b975  call    ?SetMinimumKeyCount@@YAJPEBU_PregenParms@@@Z; SetMinimumKeyCount(_PregenParms const *)
0x18001b97a  test    eax, eax
0x18001b97c  jns     short loc_18001B997
0x18001b97e  mov     rcx, [rsp+28h]; this
0x18001b983  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b98a  mov     r9d, eax; char *
0x18001b98d  mov     edx, 109h; void *
0x18001b992  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b997  cmp     dword ptr [rbx], 1
0x18001b99a  jnz     short loc_18001B9C6
0x18001b99c  test    rdi, rdi
0x18001b99f  jz      short loc_18001B9C6
0x18001b9a1  mov     rcx, rdi; enum DelayRetryAction *
0x18001b9a4  call    ?GetAikEnrollRetryType@@YAJPEAW4DelayRetryAction@@@Z; GetAikEnrollRetryType(DelayRetryAction *)
0x18001b9a9  test    eax, eax
0x18001b9ab  jns     short loc_18001B9C6
0x18001b9ad  mov     rcx, [rsp+28h]; this
0x18001b9b2  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001b9b9  mov     r9d, eax; char *
0x18001b9bc  mov     edx, 113h; void *
0x18001b9c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b9c6  test    sil, sil
0x18001b9c9  jz      short loc_18001BA14
0x18001b9cb  mov     ecx, [rsp+28h+arg_20]
0x18001b9cf  test    ecx, ecx
0x18001b9d1  jz      short loc_18001BA14
0x18001b9d3  cmp     ecx, 3
0x18001b9d6  jz      short loc_18001B9E8
0x18001b9d8  call    NgcTriggerTask
0x18001b9dd  test    eax, eax
0x18001b9df  jns     short loc_18001BA0C
0x18001b9e1  mov     edx, 122h
0x18001b9e6  jmp     short loc_18001B9F8
0x18001b9e8  mov     cl, 1; bool
0x18001b9ea  call    ?ChangeKeyPregenTaskTriggersStatus@@YAJ_N@Z; ChangeKeyPregenTaskTriggersStatus(bool)
0x18001b9ef  test    eax, eax
0x18001b9f1  jns     short loc_18001BA0C
0x18001b9f3  mov     edx, 129h; void *
0x18001b9f8  mov     rcx, [rsp+28h]; this
0x18001b9fd  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ba04  mov     r9d, eax; char *
0x18001ba07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ba0c  mov     rax, [rsp+28h+arg_28]
0x18001ba11  mov     byte ptr [rax], 1
0x18001ba14  mov     rbx, [rsp+28h+arg_0]
0x18001ba19  mov     rsi, [rsp+28h+arg_8]
0x18001ba1e  add     rsp, 20h
0x18001ba22  pop     rdi
0x18001ba23  retn
```
