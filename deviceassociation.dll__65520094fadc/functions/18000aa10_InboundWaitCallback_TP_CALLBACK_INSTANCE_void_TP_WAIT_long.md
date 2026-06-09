# InboundWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18000aa10`
- end: `0x18000ad90`
- name: `?InboundWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `896`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002f10`
- `0x18000a9e0`
- `0x18000aa10`
- `0x18000bbf0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aaa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aaa1`
- `RPCRT4!NdrClientCall3` at `0x18000abad`
- `RPCRT4!NdrClientCall3` at `0x18000abad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000ad0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000ad0c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000aa86`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000aa97`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000aa86`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000aa97`

## pseudocode

```c
void __fastcall InboundWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v7; // ebx
  int v8; // eax
  CLIENT_CALL_RETURN v9; // rbx
  void **v10; // rcx
  __int64 i; // rdi
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  unsigned int j; // r8d
  void *v15; // rcx
  unsigned int v16; // [rsp+60h] [rbp-88h] BYREF
  unsigned int v17; // [rsp+64h] [rbp-84h] BYREF
  int v18; // [rsp+68h] [rbp-80h] BYREF
  int v19; // [rsp+6Ch] [rbp-7Ch] BYREF
  unsigned int v20; // [rsp+70h] [rbp-78h] BYREF
  void *v21; // [rsp+78h] [rbp-70h] BYREF
  void *v22; // [rsp+80h] [rbp-68h] BYREF
  int Pointer; // [rsp+88h] [rbp-60h]
  void *v24; // [rsp+90h] [rbp-58h] BYREF
  CLIENT_CALL_RETURN v25; // [rsp+98h] [rbp-50h]
  char *v26; // [rsp+A0h] [rbp-48h]
  char *v27; // [rsp+A8h] [rbp-40h]
  GUID ActivityId; // [rsp+B0h] [rbp-38h] BYREF

  ActivityId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_61e63e094b87365e371089d0260af5a5_Traceguids);
  if ( !EventActivityIdControl(1u, &ActivityId) )
    EventActivityIdControl(2u, (LPGUID)Context + 7);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 16));
  v7 = *((_DWORD *)Context + 20);
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 16));
  if ( v7 )
  {
    if ( WaitResult )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, int))Context + 16))(
        0,
        0,
        0,
        0,
        0,
        0,
        *((_QWORD *)Context + 13),
        -2147467259);
    }
    else if ( Wait == *((PTP_WAIT *)Context + 20) )
    {
      v26 = Context;
      v27 = Context + 160;
      v8 = 1;
      v18 = 1;
LABEL_10:
      if ( v8 )
      {
        while ( 1 )
        {
          v24 = 0;
          v16 = 0;
          v21 = 0;
          v20 = 0;
          v17 = 0;
          v22 = 0;
          v19 = 0;
          v25.Simple = 0;
          v9.Pointer = NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&Inbound_ProxyInfo,
                         2u,
                         0,
                         Context + 56,
                         &v24,
                         &v16,
                         &v21,
                         &v20,
                         &v17,
                         &v22,
                         &v19,
                         &v18).Pointer;
          v25.Pointer = v9.Pointer;
          Pointer = (int)v9.Pointer;
          if ( LODWORD(v9.Pointer) == -2140930012 )
            break;
          (*((void (__fastcall **)(void *, _QWORD, void *, _QWORD, unsigned int, void *, _QWORD, int))Context + 16))(
            v24,
            v16,
            v21,
            v20,
            v17,
            v22,
            *((_QWORD *)Context + 13),
            v19);
          if ( v24 )
            MIDL_user_free(v24);
          v10 = (void **)v21;
          if ( v21 )
          {
            for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
            {
              if ( v10[6 * i + 5] )
              {
                MIDL_user_free(v10[6 * i + 5]);
                v10 = (void **)v21;
              }
              if ( v10[6 * i + 3] )
              {
                MIDL_user_free(v10[6 * i + 3]);
                v10 = (void **)v21;
              }
            }
            MIDL_user_free(v10);
          }
          v12 = v22;
          if ( v22 )
          {
            v13 = 0;
            for ( j = v17; (unsigned int)v13 < j; v13 = (unsigned int)(v13 + 1) )
            {
              v15 = (void *)v12[5 * v13 + 4];
              if ( v15 )
              {
                MIDL_user_free(v15);
                j = v17;
                v12 = v22;
              }
            }
            MIDL_user_free(v12);
          }
          if ( SLODWORD(v9.Simple) < 0 )
            break;
          if ( !v18 )
          {
            SetThreadpoolWait(*((PTP_WAIT *)Context + 20), *((HANDLE *)Context + 19), 0);
            v8 = v18;
            goto LABEL_10;
          }
        }
      }
    }
    else if ( Wait == *((PTP_WAIT *)Context + 18) )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, int))Context + 16))(
        0,
        0,
        0,
        0,
        0,
        0,
        *((_QWORD *)Context + 13),
        -2147467260);
    }
  }
}

```

## disassembly

```asm
0x18000aa10  mov     r11, rsp
0x18000aa13  mov     [r11+8], rbx
0x18000aa17  mov     [r11+18h], rdi
0x18000aa1b  push    r12
0x18000aa1d  push    r14
0x18000aa1f  push    r15
0x18000aa21  sub     rsp, 0D0h
0x18000aa28  mov     rax, cs:__security_cookie
0x18000aa2f  xor     rax, rsp
0x18000aa32  mov     [rsp+0E8h+var_28], rax
0x18000aa3a  mov     r12d, r9d
0x18000aa3d  mov     r15, r8
0x18000aa40  mov     r14, rdx
0x18000aa43  xorps   xmm0, xmm0
0x18000aa46  movups  xmmword ptr [r11-38h], xmm0
0x18000aa4b  lea     rax, WPP_GLOBAL_Control
0x18000aa52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa59  cmp     rcx, rax
0x18000aa5c  jz      short loc_18000AA79
0x18000aa5e  cmp     byte ptr [rcx+19h], 4
0x18000aa62  jb      short loc_18000AA79
0x18000aa64  mov     edx, 0Ch
0x18000aa69  lea     r8, WPP_61e63e094b87365e371089d0260af5a5_Traceguids
0x18000aa70  mov     rcx, [rcx+10h]
0x18000aa74  call    WPP_SF_s
0x18000aa79  lea     rdx, [rsp+0E8h+ActivityId]; ActivityId
0x18000aa81  mov     ecx, 1; ControlCode
0x18000aa86  call    cs:__imp_EventActivityIdControl
0x18000aa8c  test    eax, eax
0x18000aa8e  jnz     short loc_18000AA9D
0x18000aa90  lea     rdx, [r14+70h]; ActivityId
0x18000aa94  lea     ecx, [rax+2]; ControlCode
0x18000aa97  call    cs:__imp_EventActivityIdControl
0x18000aa9d  lea     rcx, [r14+10h]; lpCriticalSection
0x18000aaa1  call    cs:__imp_EnterCriticalSection
0x18000aaa7  mov     ebx, [r14+50h]
0x18000aaab  lea     rcx, [r14+10h]; lpCriticalSection
0x18000aaaf  call    cs:__imp_LeaveCriticalSection
0x18000aab5  test    ebx, ebx
0x18000aab7  jz      loc_18000AD66
0x18000aabd  test    r12d, r12d
0x18000aac0  jnz     loc_18000AD2E
0x18000aac6  lea     r12, [r14+0A0h]
0x18000aacd  cmp     r15, [r12]
0x18000aad1  jnz     loc_18000AD1B
0x18000aad7  mov     [rsp+0E8h+var_48], r14
0x18000aadf  mov     [rsp+0E8h+var_40], r12
0x18000aae7  mov     eax, 1
0x18000aaec  mov     [rsp+0E8h+var_80], eax
0x18000aaf0  test    eax, eax
0x18000aaf2  jz      loc_18000AD66
0x18000aaf8  mov     [rsp+0E8h+var_58], 0
0x18000ab04  mov     [rsp+0E8h+var_88], 0
0x18000ab0c  mov     [rsp+0E8h+var_70], 0
0x18000ab15  mov     [rsp+0E8h+var_78], 0
0x18000ab1d  mov     [rsp+0E8h+var_84], 0
0x18000ab25  mov     [rsp+0E8h+var_68], 0
0x18000ab31  mov     [rsp+0E8h+var_7C], 0
0x18000ab39  mov     [rsp+0E8h+var_50], 0
0x18000ab45  lea     r9, [r14+38h]
0x18000ab49  lea     rax, [rsp+0E8h+var_80]
0x18000ab4e  mov     [rsp+0E8h+var_90], rax
0x18000ab53  lea     rax, [rsp+0E8h+var_7C]
0x18000ab58  mov     [rsp+0E8h+var_98], rax
0x18000ab5d  lea     rax, [rsp+0E8h+var_68]
0x18000ab65  mov     [rsp+0E8h+var_A0], rax
0x18000ab6a  lea     rax, [rsp+0E8h+var_84]
0x18000ab6f  mov     [rsp+0E8h+var_A8], rax
0x18000ab74  lea     rax, [rsp+0E8h+var_78]
0x18000ab79  mov     [rsp+0E8h+var_B0], rax
0x18000ab7e  lea     rax, [rsp+0E8h+var_70]
0x18000ab83  mov     [rsp+0E8h+var_B8], rax
0x18000ab88  lea     rax, [rsp+0E8h+var_88]
0x18000ab8d  mov     [rsp+0E8h+var_C0], rax
0x18000ab92  lea     rax, [rsp+0E8h+var_58]
0x18000ab9a  mov     [rsp+0E8h+var_C8], rax
0x18000ab9f  xor     r8d, r8d; pReturnValue
0x18000aba2  lea     edx, [r8+2]; nProcNum
0x18000aba6  lea     rcx, ?Inbound_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000abad  call    cs:__imp_NdrClientCall3
0x18000abb3  mov     rbx, rax
0x18000abb6  mov     [rsp+0E8h+var_50], rax
0x18000abbe  mov     [rsp+0E8h+var_60], eax
0x18000abc5  cmp     eax, 80640024h
0x18000abca  jz      loc_18000AD66
0x18000abd0  mov     eax, [rsp+0E8h+var_7C]
0x18000abd4  mov     dword ptr [rsp+0E8h+var_B0], eax
0x18000abd8  mov     rcx, [r14+68h]
0x18000abdc  mov     [rsp+0E8h+var_B8], rcx
0x18000abe1  mov     rcx, [rsp+0E8h+var_68]
0x18000abe9  mov     [rsp+0E8h+var_C0], rcx
0x18000abee  mov     ecx, [rsp+0E8h+var_84]
0x18000abf2  mov     dword ptr [rsp+0E8h+var_C8], ecx
0x18000abf6  mov     r9d, [rsp+0E8h+var_78]
0x18000abfb  mov     r8, [rsp+0E8h+var_70]
0x18000ac00  mov     edx, [rsp+0E8h+var_88]
0x18000ac04  mov     rcx, [rsp+0E8h+var_58]
0x18000ac0c  mov     rax, [r14+80h]
0x18000ac13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac18  jmp     short loc_18000AC40
0x18000ac1a  cmp     eax, 1
0x18000ac1d  jl      short loc_18000AC27
0x18000ac1f  movzx   eax, ax
0x18000ac22  or      eax, 80010000h
0x18000ac27  mov     ebx, eax
0x18000ac29  mov     [rsp+0E8h+var_60], eax
0x18000ac30  mov     r14, [rsp+0E8h+var_48]
0x18000ac38  mov     r12, [rsp+0E8h+var_40]
0x18000ac40  mov     rcx, [rsp+0E8h+var_58]; void *
0x18000ac48  test    rcx, rcx
0x18000ac4b  jz      short loc_18000AC52
0x18000ac4d  call    MIDL_user_free
0x18000ac52  mov     rcx, [rsp+0E8h+var_70]
0x18000ac57  test    rcx, rcx
0x18000ac5a  jz      short loc_18000ACA6
0x18000ac5c  xor     edi, edi
0x18000ac5e  cmp     [rsp+0E8h+var_88], edi
0x18000ac62  jbe     short loc_18000ACA1
0x18000ac64  lea     r15, [rdi+rdi*2]
0x18000ac68  add     r15, r15
0x18000ac6b  mov     rax, [rcx+r15*8+28h]
0x18000ac70  test    rax, rax
0x18000ac73  jz      short loc_18000AC82
0x18000ac75  mov     rcx, rax; void *
0x18000ac78  call    MIDL_user_free
0x18000ac7d  mov     rcx, [rsp+0E8h+var_70]
0x18000ac82  mov     rax, [rcx+r15*8+18h]
0x18000ac87  test    rax, rax
0x18000ac8a  jz      short loc_18000AC99
0x18000ac8c  mov     rcx, rax; void *
0x18000ac8f  call    MIDL_user_free
0x18000ac94  mov     rcx, [rsp+0E8h+var_70]; void *
0x18000ac99  inc     edi
0x18000ac9b  cmp     edi, [rsp+0E8h+var_88]
0x18000ac9f  jb      short loc_18000AC64
0x18000aca1  call    MIDL_user_free
0x18000aca6  mov     rdx, [rsp+0E8h+var_68]
0x18000acae  test    rdx, rdx
0x18000acb1  jz      short loc_18000ACEE
0x18000acb3  xor     edi, edi
0x18000acb5  mov     r8d, [rsp+0E8h+var_84]
0x18000acba  test    r8d, r8d
0x18000acbd  jz      short loc_18000ACE6
0x18000acbf  lea     rcx, [rdi+rdi*4]
0x18000acc3  mov     rcx, [rdx+rcx*8+20h]; void *
0x18000acc8  test    rcx, rcx
0x18000accb  jz      short loc_18000ACDF
0x18000accd  call    MIDL_user_free
0x18000acd2  mov     r8d, [rsp+0E8h+var_84]
0x18000acd7  mov     rdx, [rsp+0E8h+var_68]
0x18000acdf  inc     edi
0x18000ace1  cmp     edi, r8d
0x18000ace4  jb      short loc_18000ACBF
0x18000ace6  mov     rcx, rdx; void *
0x18000ace9  call    MIDL_user_free
0x18000acee  test    ebx, ebx
0x18000acf0  js      short loc_18000AD66
0x18000acf2  mov     eax, [rsp+0E8h+var_80]
0x18000acf6  test    eax, eax
0x18000acf8  jnz     loc_18000AAF8
0x18000acfe  xor     r8d, r8d; pftTimeout
0x18000ad01  mov     rdx, [r14+98h]; h
0x18000ad08  mov     rcx, [r12]; pwa
0x18000ad0c  call    cs:__imp_SetThreadpoolWait
0x18000ad12  mov     eax, [rsp+0E8h+var_80]
0x18000ad16  jmp     loc_18000AAF0
0x18000ad1b  cmp     r15, [r14+90h]
0x18000ad22  jnz     short loc_18000AD66
0x18000ad24  mov     dword ptr [rsp+0E8h+var_B0], 80004004h
0x18000ad2c  jmp     short loc_18000AD36
0x18000ad2e  mov     dword ptr [rsp+0E8h+var_B0], 80004005h
0x18000ad36  mov     rcx, [r14+68h]
0x18000ad3a  mov     [rsp+0E8h+var_B8], rcx
0x18000ad3f  mov     [rsp+0E8h+var_C0], 0
0x18000ad48  mov     dword ptr [rsp+0E8h+var_C8], 0
0x18000ad50  xor     r9d, r9d
0x18000ad53  xor     r8d, r8d
0x18000ad56  xor     edx, edx
0x18000ad58  xor     ecx, ecx
0x18000ad5a  mov     rax, [r14+80h]
0x18000ad61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad66  mov     rcx, [rsp+0E8h+var_28]
0x18000ad6e  xor     rcx, rsp; StackCookie
0x18000ad71  call    __security_check_cookie
0x18000ad76  lea     r11, [rsp+0E8h+var_18]
0x18000ad7e  mov     rbx, [r11+20h]
0x18000ad82  mov     rdi, [r11+30h]
0x18000ad86  mov     rsp, r11
0x18000ad89  pop     r15
0x18000ad8b  pop     r14
0x18000ad8d  pop     r12
0x18000ad8f  retn
0x18000c09c  push    rbp
0x18000c09e  sub     rsp, 60h
0x18000c0a2  mov     rbp, rdx
0x18000c0a5  mov     rcx, [rcx]
0x18000c0a8  mov     ecx, [rcx]; ExceptionCode
0x18000c0aa  call    cs:__imp_RpcExceptionFilter
0x18000c0b0  nop
0x18000c0b1  add     rsp, 60h
0x18000c0b5  pop     rbp
0x18000c0b6  retn
```
