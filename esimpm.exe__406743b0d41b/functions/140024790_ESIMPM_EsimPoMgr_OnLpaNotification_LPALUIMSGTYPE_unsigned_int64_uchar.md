# ESIMPM::EsimPoMgr::OnLpaNotification(LPALUIMSGTYPE,unsigned __int64,uchar *)

- ea: `0x140024790`
- end: `0x140024864`
- name: `?OnLpaNotification@EsimPoMgr@ESIMPM@@UEAAXW4LPALUIMSGTYPE@@_KPEAE@Z`
- size: `212`
- prototype: `void __high(enum LPALUIMSGTYPE, unsigned __int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x140020620`
- `0x140024790`
- `0x1400311ec`
- `0x1400312d4`
- `0x14003154c`
- `0x140031c00`

## string_xrefs

- `0x1400247cc`: `LpaCallback, lui is null, Uninitialize() is called already, skip`

## pseudocode

```c
void __fastcall ESIMPM::EsimPoMgr::OnLpaNotification(
        __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        const struct LPA_PROFILE_DETAILS *a4)
{
  ESIMPM::LpaHelper *v5; // rbp
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx

  v5 = (ESIMPM::LpaHelper *)(a1 + 128);
  ESIMPM::Log::Info("ESIMPM::LpaHelper::OnLpaNotification", 0, L"type %d, cbBuffer %d", a2, a3);
  if ( *(_QWORD *)v5 )
  {
    v8 = a2 - 2;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 == 1 && a4 && a3 >= 0x3F0 )
            ESIMPM::LpaHelper::ProcessProfileDetails(v5, a4);
        }
        else if ( a4 && a3 >= 0x2D0 )
        {
          ESIMPM::LpaHelper::ProcessEsimDetails(v5, a4);
        }
      }
      else if ( a4 && a3 >= 0x14 )
      {
        ESIMPM::LpaHelper::ProcessServiceInfo(v5, a4);
      }
    }
    else if ( a4 && a3 >= 0x14 )
    {
      ESIMPM::LpaHelper::ProcessAsyncResult(v5, a4);
    }
  }
  else
  {
    ESIMPM::Log::Info(
      "ESIMPM::LpaHelper::OnLpaNotification",
      0,
      L"LpaCallback, lui is null, Uninitialize() is called already, skip");
  }
}

```

## disassembly

```asm
0x140024790  push    rbx
0x140024792  push    rbp
0x140024793  push    rsi
0x140024794  push    rdi
0x140024795  sub     rsp, 38h
0x140024799  mov     rdi, r9
0x14002479c  mov     [rsp+58h+var_38], r8
0x1400247a1  mov     r9d, edx
0x1400247a4  lea     rbp, [rcx+80h]
0x1400247ab  mov     rsi, r8
0x1400247ae  lea     rcx, aEsimpmLpahelpe_5; "ESIMPM::LpaHelper::OnLpaNotification"
0x1400247b5  mov     ebx, edx
0x1400247b7  lea     r8, aTypeDCbbufferD; "type %d, cbBuffer %d"
0x1400247be  xor     edx, edx; struct _GUID *
0x1400247c0  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x1400247c5  cmp     qword ptr [rbp+0], 0
0x1400247ca  jnz     short loc_1400247E3
0x1400247cc  lea     r8, aLpacallbackLui; "LpaCallback, lui is null, Uninitialize("...
0x1400247d3  xor     edx, edx; struct _GUID *
0x1400247d5  lea     rcx, aEsimpmLpahelpe_5; "ESIMPM::LpaHelper::OnLpaNotification"
0x1400247dc  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x1400247e1  jmp     short loc_14002485B
0x1400247e3  sub     ebx, 2
0x1400247e6  jz      short loc_140024845
0x1400247e8  sub     ebx, 1
0x1400247eb  jz      short loc_14002482D
0x1400247ed  sub     ebx, 1
0x1400247f0  jz      short loc_140024812
0x1400247f2  cmp     ebx, 1
0x1400247f5  jnz     short loc_14002485B
0x1400247f7  test    rdi, rdi
0x1400247fa  jz      short loc_14002485B
0x1400247fc  cmp     rsi, 3F0h
0x140024803  jb      short loc_14002485B
0x140024805  mov     rdx, rdi; Source
0x140024808  mov     rcx, rbp; this
0x14002480b  call    ?ProcessProfileDetails@LpaHelper@ESIMPM@@AEAAXPEBULPA_PROFILE_DETAILS@@@Z; ESIMPM::LpaHelper::ProcessProfileDetails(LPA_PROFILE_DETAILS const *)
0x140024810  jmp     short loc_14002485B
0x140024812  test    rdi, rdi
0x140024815  jz      short loc_14002485B
0x140024817  cmp     rsi, 2D0h
0x14002481e  jb      short loc_14002485B
0x140024820  mov     rdx, rdi; Source
0x140024823  mov     rcx, rbp; this
0x140024826  call    ?ProcessEsimDetails@LpaHelper@ESIMPM@@AEAAXPEBULPA_ESIM_DETAILS@@@Z; ESIMPM::LpaHelper::ProcessEsimDetails(LPA_ESIM_DETAILS const *)
0x14002482b  jmp     short loc_14002485B
0x14002482d  test    rdi, rdi
0x140024830  jz      short loc_14002485B
0x140024832  cmp     rsi, 14h
0x140024836  jb      short loc_14002485B
0x140024838  mov     rdx, rdi; struct LPA_SERVICE_INFO *
0x14002483b  mov     rcx, rbp; this
0x14002483e  call    ?ProcessServiceInfo@LpaHelper@ESIMPM@@AEAAXPEBULPA_SERVICE_INFO@@@Z; ESIMPM::LpaHelper::ProcessServiceInfo(LPA_SERVICE_INFO const *)
0x140024843  jmp     short loc_14002485B
0x140024845  test    rdi, rdi
0x140024848  jz      short loc_14002485B
0x14002484a  cmp     rsi, 14h
0x14002484e  jb      short loc_14002485B
0x140024850  mov     rdx, rdi; struct LPA_ASYNC_RESULT *
0x140024853  mov     rcx, rbp; this
0x140024856  call    ?ProcessAsyncResult@LpaHelper@ESIMPM@@AEAAXPEBULPA_ASYNC_RESULT@@@Z; ESIMPM::LpaHelper::ProcessAsyncResult(LPA_ASYNC_RESULT const *)
0x14002485b  add     rsp, 38h
0x14002485f  pop     rdi
0x140024860  pop     rsi
0x140024861  pop     rbp
0x140024862  pop     rbx
0x140024863  retn
```
