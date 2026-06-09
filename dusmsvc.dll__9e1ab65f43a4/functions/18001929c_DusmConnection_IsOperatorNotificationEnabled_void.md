# DusmConnection::IsOperatorNotificationEnabled(void)

- ea: `0x18001929c`
- end: `0x1800193d0`
- name: `?IsOperatorNotificationEnabled@DusmConnection@@AEBA_NXZ`
- size: `308`
- prototype: `bool __fastcall(DusmConnection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018fa8`

## callees

- `0x180007c90`
- `0x180012fcc`
- `0x1800182ec`
- `0x18001842c`
- `0x18001929c`

## import_xrefs

- `wcmapi!WcmQueryParameter` at `0x180019350`
- `wcmapi!WcmQueryParameter` at `0x180019350`
- `wcmapi!WcmFreeMemory` at `0x180019387`
- `wcmapi!WcmFreeMemory` at `0x18001939c`
- `wcmapi!WcmFreeMemory` at `0x180019387`
- `wcmapi!WcmFreeMemory` at `0x18001939c`
- `wcmapi!WcmOpenHandle` at `0x1800192e3`
- `wcmapi!WcmOpenHandle` at `0x1800192e3`

## pseudocode

```c
bool __fastcall DusmConnection::IsOperatorNotificationEnabled(DusmConnection *this)
{
  bool v2; // zf
  __int64 v3; // rax
  int v4; // ebx
  __int64 v5; // rcx
  bool v6; // bl
  __int64 *v8; // [rsp+40h] [rbp+7h] BYREF
  __int64 v9; // [rsp+48h] [rbp+Fh] BYREF
  char v10; // [rsp+50h] [rbp+17h]
  __int64 *v11; // [rsp+58h] [rbp+1Fh] BYREF
  char v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh] BYREF
  int v14; // [rsp+70h] [rbp+37h] BYREF
  __int64 v15; // [rsp+78h] [rbp+3Fh] BYREF
  int v16; // [rsp+80h] [rbp+47h] BYREF

  v13 = 0;
  v16 = 0;
  v11 = &v13;
  if ( (unsigned int)WcmOpenHandle(1, 0, &v16, &v13) )
  {
LABEL_12:
    v6 = 0;
    goto LABEL_13;
  }
  v14 = 0;
  v2 = *((_QWORD *)this + 8) == 0;
  v8 = &v15;
  v15 = 0;
  v9 = 0;
  v10 = 1;
  if ( v2 )
    v3 = 0;
  else
    v3 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 48);
  v4 = WcmQueryParameter(v13, (char *)this + 32, v3, 264, 0, &v14, &v9);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WCM_PLAN_POLICY,wil::function_deleter<void (*)(void *),&void WcmFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WCM_PLAN_POLICY,wil::function_deleter<void (*)(void *),&void WcmFreeMemory(void *)>>>(&v8);
  v5 = v15;
  if ( v4 || !v15 || v14 != 12 )
  {
    v15 = 0;
    if ( v5 )
      WcmFreeMemory(v5);
    goto LABEL_12;
  }
  v2 = *(_DWORD *)(v15 + 8) == 0;
  v15 = 0;
  v6 = !v2;
  if ( v5 )
    WcmFreeMemory(v5);
LABEL_13:
  v12 = 0;
  DusmPublishToWcm_::_2_::_lambda_1_::operator()(&v11);
  return v6;
}

```

## disassembly

```asm
0x18001929c  mov     [rsp-8+arg_8], rbx
0x1800192a1  push    rbp
0x1800192a2  lea     rbp, [rsp-57h]
0x1800192a7  sub     rsp, 90h
0x1800192ae  mov     rax, cs:__security_cookie
0x1800192b5  xor     rax, rsp
0x1800192b8  mov     [rbp+57h+var_8], rax
0x1800192bc  xor     edx, edx
0x1800192be  mov     [rbp+57h+var_28], 0
0x1800192c6  mov     rbx, rcx
0x1800192c9  mov     [rbp+57h+var_10], 0
0x1800192d0  lea     rax, [rbp+57h+var_28]
0x1800192d4  lea     r9, [rbp+57h+var_28]
0x1800192d8  mov     [rbp+57h+var_38], rax
0x1800192dc  lea     ecx, [rdx+1]
0x1800192df  lea     r8, [rbp+57h+var_10]
0x1800192e3  call    cs:__imp_WcmOpenHandle
0x1800192e9  test    eax, eax
0x1800192eb  jnz     loc_1800193A2
0x1800192f1  mov     [rbp+57h+var_20], eax
0x1800192f4  lea     rcx, [rbx+30h]
0x1800192f8  cmp     qword ptr [rcx+10h], 0
0x1800192fd  lea     rax, [rbp+57h+var_18]
0x180019301  mov     [rbp+57h+var_50], rax
0x180019305  mov     [rbp+57h+var_18], 0
0x18001930d  mov     [rbp+57h+var_48], 0
0x180019315  mov     [rbp+57h+var_40], 1
0x180019319  jnz     short loc_18001931F
0x18001931b  xor     eax, eax
0x18001931d  jmp     short loc_180019324
0x18001931f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019324  lea     rcx, [rbp+57h+var_48]
0x180019328  mov     r9d, 108h
0x18001932e  mov     [rsp+90h+var_60], rcx
0x180019333  lea     rdx, [rbx+20h]
0x180019337  lea     rcx, [rbp+57h+var_20]
0x18001933b  mov     r8, rax
0x18001933e  mov     [rsp+90h+var_68], rcx
0x180019343  mov     rcx, [rbp+57h+var_28]
0x180019347  mov     [rsp+90h+var_70], 0
0x180019350  call    cs:__imp_WcmQueryParameter
0x180019356  lea     rcx, [rbp+57h+var_50]
0x18001935a  mov     ebx, eax
0x18001935c  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@U_WCM_PLAN_POLICY@@U?$function_deleter@P6AXPEAX@Z$1?WcmFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<_WCM_PLAN_POLICY,wil::function_deleter<void (*)(void *),&WcmFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<_WCM_PLAN_POLICY,wil::function_deleter<void (*)(void *),&WcmFreeMemory(void *)>>>(void)
0x180019361  mov     rcx, [rbp+57h+var_18]
0x180019365  test    ebx, ebx
0x180019367  jnz     short loc_18001938F
0x180019369  test    rcx, rcx
0x18001936c  jz      short loc_18001938F
0x18001936e  cmp     [rbp+57h+var_20], 0Ch
0x180019372  jnz     short loc_18001938F
0x180019374  cmp     [rcx+8], ebx
0x180019377  mov     [rbp+57h+var_18], 0
0x18001937f  setnz   bl
0x180019382  test    rcx, rcx
0x180019385  jz      short loc_1800193A4
0x180019387  call    cs:__imp_WcmFreeMemory
0x18001938d  jmp     short loc_1800193A4
0x18001938f  mov     [rbp+57h+var_18], 0
0x180019397  test    rcx, rcx
0x18001939a  jz      short loc_1800193A2
0x18001939c  call    cs:__imp_WcmFreeMemory
0x1800193a2  xor     ebx, ebx
0x1800193a4  lea     rcx, [rbp+57h+var_38]
0x1800193a8  mov     [rbp+57h+var_30], 0
0x1800193ac  call    _DusmPublishToWcm____2____lambda_1___operator__
0x1800193b1  mov     al, bl
0x1800193b3  mov     rcx, [rbp+57h+var_8]
0x1800193b7  xor     rcx, rsp; StackCookie
0x1800193ba  call    __security_check_cookie
0x1800193bf  mov     rbx, [rsp+90h+arg_8]
0x1800193c7  add     rsp, 90h
0x1800193ce  pop     rbp
0x1800193cf  retn
```
