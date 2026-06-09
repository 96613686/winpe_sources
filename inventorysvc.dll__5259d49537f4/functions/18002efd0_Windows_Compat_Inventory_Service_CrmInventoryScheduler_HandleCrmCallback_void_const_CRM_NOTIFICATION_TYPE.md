# Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback(void * const,_CRM_NOTIFICATION_TYPE)

- ea: `0x18002efd0`
- end: `0x18002f428`
- name: `?HandleCrmCallback@CrmInventoryScheduler@Service@Inventory@Compat@Windows@@AEAAXQEAXW4_CRM_NOTIFICATION_TYPE@@@Z`
- size: `1112`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ef20`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x1800108d4`
- `0x1800152d0`
- `0x18002cbc0`
- `0x18002efd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f257`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f280`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f2d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f2fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f257`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f280`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f2d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f2fe`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f245`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f26e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f2ea`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f30c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f245`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f26e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f2ea`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f30c`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFreeWindowClosedReasons` at `0x18002f236`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFreeWindowClosedReasons` at `0x18002f236`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityQueryWindowClosedReasons` at `0x18002f129`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityQueryWindowClosedReasons` at `0x18002f129`

## string_xrefs

- `0x18002f367`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f380`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f399`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f416`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f3b2`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002f3cb`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002f3e4`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002f3fd`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002f038`: `Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback`
- `0x18002f0fa`: `Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback`
- `0x18002f220`: `Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback`
- `0x18002f2b6`: `Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback`
- `0x18002f33a`: `Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback`
- `0x18002f2af`: `CrmNotificationTypeActivityWindowOpen %hsNetwork %p`

## pseudocode

```c
int __fastcall Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback(
        __int64 a1,
        __int64 a2,
        int a3)
{
  char v5; // si
  int result; // eax
  const char *v7; // rcx
  const char *v8; // rcx
  const char *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rdx
  char *v12; // rax
  __int64 v13; // r8
  char *v14; // r9
  __int64 v15; // rax
  char *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rax
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // rcx
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  unsigned int v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  char v30[16]; // [rsp+50h] [rbp-B0h] BYREF
  char v31[272]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  if ( a2 == *(_QWORD *)(a1 + 128) )
  {
    v5 = 1;
  }
  else
  {
    if ( a2 != *(_QWORD *)(a1 + 136) )
      return AslLogCallPrintf(
               1,
               "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
               113,
               "Unknown CRM activity %p: [%#x]",
               a2,
               -2147418113);
    v5 = 0;
  }
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
      case 2:
        v8 = (const char *)&word_1800D7582;
        if ( !v5 )
          v8 = "Non";
        v9 = "CrmNotificationTypeActivityWindowClosed";
        if ( a3 != 1 )
          v9 = "CrmNotificationTypeActivityExpiration";
        AslLogCallPrintf(
          3,
          "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
          141,
          "%hs %hsNetwork %p",
          v9,
          v8,
          a2);
        v29 = 0;
        v28 = 0;
        if ( (int)CrmActivityQueryWindowClosedReasons(a2, &v29, &v28) >= 0 )
        {
          memset_0(v31, 0, 0x104u);
          v10 = 0;
          if ( v28 )
          {
            while ( (int)StringCchPrintfA(v30, 0x10u, "%d ", *(_DWORD *)(v29 + 4 * v10)) >= 0 )
            {
              v11 = 260;
              v12 = v31;
              do
              {
                if ( !*v12 )
                  break;
                ++v12;
                --v11;
              }
              while ( v11 );
              v13 = (260 - v11) & -(__int64)(v11 != 0);
              if ( !v11 )
                break;
              v14 = v30;
              v15 = 2147483646;
              v16 = &v31[v13];
              v17 = 260 - v13;
              if ( v13 != 260 )
              {
                do
                {
                  if ( !v15 )
                    break;
                  if ( !*v14 )
                    break;
                  *v16++ = *v14++;
                  --v15;
                  --v17;
                }
                while ( v17 );
              }
              v18 = v16 - 1;
              if ( v17 )
                v18 = v16;
              *v18 = 0;
              if ( !v17 )
                break;
              v10 = (unsigned int)(v10 + 1);
              if ( (unsigned int)v10 >= v28 )
                goto LABEL_37;
            }
            v31[0] = 0;
          }
LABEL_37:
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
            159,
            "CrmNotificationTypeActivityWindowClosed Reasons:%hs",
            v31);
          CrmActivityFreeWindowClosedReasons(v29);
        }
        if ( v5 )
        {
          if ( !ResetEvent(*(HANDLE *)(a1 + 48)) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA06,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
              v19);
          result = SetEvent(*(HANDLE *)(a1 + 64));
          if ( !result )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA01,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v20);
        }
        else
        {
          if ( !ResetEvent(*(HANDLE *)(a1 + 56)) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA06,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
              v21);
          result = SetEvent(*(HANDLE *)(a1 + 72));
          if ( !result )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA01,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v22);
        }
        break;
      case 3:
        v7 = (const char *)&word_1800D7582;
        if ( !v5 )
          v7 = "Non";
        return AslLogCallPrintf(
                 3,
                 "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
                 175,
                 "CrmNotificationTypeActivityDeadlineExpiration %hsNetwork %p",
                 v7,
                 a2);
      case 4:
        return AslLogCallPrintf(
                 3,
                 "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
                 120,
                 "CrmNotificationTypeMax %p",
                 a2);
      default:
        return AslLogCallPrintf(
                 1,
                 "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
                 178,
                 "Unknown CRM notification type [%d]",
                 a3);
    }
  }
  else
  {
    v23 = (const char *)&word_1800D7582;
    if ( !v5 )
      v23 = "Non";
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::CrmInventoryScheduler::HandleCrmCallback",
      123,
      "CrmNotificationTypeActivityWindowOpen %hsNetwork %p",
      v23,
      a2);
    if ( v5 )
    {
      if ( !SetEvent(*(HANDLE *)(a1 + 48)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v24);
      result = ResetEvent(*(HANDLE *)(a1 + 64));
      if ( !result )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA06,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v25);
    }
    else
    {
      if ( !SetEvent(*(HANDLE *)(a1 + 56)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v26);
      result = ResetEvent(*(HANDLE *)(a1 + 72));
      if ( !result )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA06,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v27);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002efd0  push    rbp
0x18002efd2  push    rbx
0x18002efd3  push    rsi
0x18002efd4  push    rdi
0x18002efd5  push    r12
0x18002efd7  lea     rbp, [rsp-80h]
0x18002efdc  sub     rsp, 180h
0x18002efe3  mov     rax, cs:__security_cookie
0x18002efea  xor     rax, rsp
0x18002efed  mov     [rbp+0A0h+var_30], rax
0x18002eff1  mov     rdi, rdx
0x18002eff4  mov     rbx, rcx
0x18002eff7  cmp     rdx, [rcx+80h]
0x18002effe  jnz     short loc_18002F005
0x18002f000  mov     sil, 1
0x18002f003  jmp     short loc_18002F015
0x18002f005  cmp     rdi, [rcx+88h]
0x18002f00c  jnz     loc_18002F31C
0x18002f012  xor     sil, sil
0x18002f015  mov     ecx, r8d
0x18002f018  test    r8d, r8d
0x18002f01b  jz      loc_18002F293
0x18002f021  sub     ecx, 1
0x18002f024  jz      loc_18002F0B3
0x18002f02a  sub     ecx, 1
0x18002f02d  jz      loc_18002F0B3
0x18002f033  sub     ecx, 1
0x18002f036  jz      short loc_18002F07D
0x18002f038  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::Service::Cr"...
0x18002f03f  cmp     ecx, 1
0x18002f042  jz      short loc_18002F05D
0x18002f044  mov     dword ptr [rsp+1A0h+var_180], r8d
0x18002f049  lea     r9, aUnknownCrmNoti; "Unknown CRM notification type [%d]"
0x18002f050  mov     r8d, 0B2h
0x18002f056  mov     ecx, 1
0x18002f05b  jmp     short loc_18002F073
0x18002f05d  mov     r8d, 78h ; 'x'
0x18002f063  mov     [rsp+1A0h+var_180], rdi
0x18002f068  lea     r9, aCrmnotificatio_0; "CrmNotificationTypeMax %p"
0x18002f06f  lea     ecx, [r8-75h]
0x18002f073  call    AslLogCallPrintf
0x18002f078  jmp     loc_18002F346
0x18002f07d  test    sil, sil
0x18002f080  mov     [rsp+1A0h+var_178], rdi
0x18002f085  lea     rax, aNon; "Non"
0x18002f08c  mov     r8d, 0AFh
0x18002f092  lea     rcx, word_1800D7582
0x18002f099  cmovz   rcx, rax
0x18002f09d  lea     r9, aCrmnotificatio_3; "CrmNotificationTypeActivityDeadlineExpi"...
0x18002f0a4  mov     [rsp+1A0h+var_180], rcx
0x18002f0a9  mov     ecx, 3
0x18002f0ae  jmp     loc_18002F33A
0x18002f0b3  test    sil, sil
0x18002f0b6  mov     [rsp+1A0h+var_170], rdi
0x18002f0bb  lea     rax, aNon; "Non"
0x18002f0c2  lea     rdx, aCrmnotificatio_2; "CrmNotificationTypeActivityExpiration"
0x18002f0c9  lea     rcx, word_1800D7582
0x18002f0d0  cmovz   rcx, rax
0x18002f0d4  lea     r9, aHsHsnetworkP; "%hs %hsNetwork %p"
0x18002f0db  cmp     r8d, 1
0x18002f0df  mov     [rsp+1A0h+var_178], rcx
0x18002f0e4  lea     rax, aCrmnotificatio; "CrmNotificationTypeActivityWindowClosed"
0x18002f0eb  mov     r8d, 8Dh
0x18002f0f1  cmovnz  rax, rdx
0x18002f0f5  mov     ecx, 3
0x18002f0fa  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::Service::Cr"...
0x18002f101  mov     [rsp+1A0h+var_180], rax
0x18002f106  call    AslLogCallPrintf
0x18002f10b  lea     r8, [rsp+1A0h+var_160]
0x18002f110  mov     [rsp+1A0h+var_158], 0
0x18002f119  lea     rdx, [rsp+1A0h+var_158]
0x18002f11e  mov     [rsp+1A0h+var_160], 0
0x18002f126  mov     rcx, rdi
0x18002f129  call    cs:__imp_CrmActivityQueryWindowClosedReasons
0x18002f12f  test    eax, eax
0x18002f131  js      loc_18002F23C
0x18002f137  mov     r12d, 104h
0x18002f13d  lea     rcx, [rsp+1A0h+var_140]; void *
0x18002f142  mov     r8d, r12d; Size
0x18002f145  xor     edx, edx; Val
0x18002f147  call    memset_0
0x18002f14c  xor     edi, edi
0x18002f14e  cmp     [rsp+1A0h+var_160], edi
0x18002f152  jbe     loc_18002F209
0x18002f158  mov     r9, [rsp+1A0h+var_158]
0x18002f15d  lea     r8, aD_1; "%d "
0x18002f164  mov     edx, 10h; unsigned __int64
0x18002f169  lea     rcx, [rsp+1A0h+var_150]; char *
0x18002f16e  mov     r9d, [r9+rdi*4]
0x18002f172  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002f177  test    eax, eax
0x18002f179  js      loc_18002F204
0x18002f17f  mov     rdx, r12
0x18002f182  lea     rax, [rsp+1A0h+var_140]
0x18002f187  cmp     byte ptr [rax], 0
0x18002f18a  jz      short loc_18002F195
0x18002f18c  inc     rax
0x18002f18f  sub     rdx, 1
0x18002f193  jnz     short loc_18002F187
0x18002f195  mov     rcx, r12
0x18002f198  mov     rax, rdx
0x18002f19b  sub     rcx, rdx
0x18002f19e  neg     rax
0x18002f1a1  sbb     r8, r8
0x18002f1a4  and     r8, rcx
0x18002f1a7  test    rdx, rdx
0x18002f1aa  jz      short loc_18002F204
0x18002f1ac  mov     rcx, r12
0x18002f1af  lea     rdx, [rsp+1A0h+var_140]
0x18002f1b4  lea     r9, [rsp+1A0h+var_150]
0x18002f1b9  mov     eax, 7FFFFFFEh
0x18002f1be  lea     rdx, [rdx+r8]
0x18002f1c2  sub     rcx, r8
0x18002f1c5  jz      short loc_18002F1E6
0x18002f1c7  test    rax, rax
0x18002f1ca  jz      short loc_18002F1E6
0x18002f1cc  mov     r8b, [r9]
0x18002f1cf  test    r8b, r8b
0x18002f1d2  jz      short loc_18002F1E6
0x18002f1d4  mov     [rdx], r8b
0x18002f1d7  inc     r9
0x18002f1da  inc     rdx
0x18002f1dd  dec     rax
0x18002f1e0  sub     rcx, 1
0x18002f1e4  jnz     short loc_18002F1C7
0x18002f1e6  test    rcx, rcx
0x18002f1e9  lea     rax, [rdx-1]
0x18002f1ed  cmovnz  rax, rdx
0x18002f1f1  mov     byte ptr [rax], 0
0x18002f1f4  jz      short loc_18002F204
0x18002f1f6  inc     edi
0x18002f1f8  cmp     edi, [rsp+1A0h+var_160]
0x18002f1fc  jb      loc_18002F158
0x18002f202  jmp     short loc_18002F209
0x18002f204  mov     [rsp+1A0h+var_140], 0
0x18002f209  lea     rax, [rsp+1A0h+var_140]
0x18002f20e  mov     r8d, 9Fh
0x18002f214  lea     r9, aCrmnotificatio_1; "CrmNotificationTypeActivityWindowClosed"...
0x18002f21b  mov     [rsp+1A0h+var_180], rax
0x18002f220  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::Service::Cr"...
0x18002f227  mov     ecx, 3
0x18002f22c  call    AslLogCallPrintf
0x18002f231  mov     rcx, [rsp+1A0h+var_158]
0x18002f236  call    cs:__imp_CrmActivityFreeWindowClosedReasons
0x18002f23c  test    sil, sil
0x18002f23f  jz      short loc_18002F26A
0x18002f241  mov     rcx, [rbx+30h]; hEvent
0x18002f245  call    cs:__imp_ResetEvent
0x18002f24b  test    eax, eax
0x18002f24d  jz      loc_18002F3DD
0x18002f253  mov     rcx, [rbx+40h]; hEvent
0x18002f257  call    cs:__imp_SetEvent
0x18002f25d  test    eax, eax
0x18002f25f  jz      loc_18002F379
0x18002f265  jmp     loc_18002F346
0x18002f26a  mov     rcx, [rbx+38h]; hEvent
0x18002f26e  call    cs:__imp_ResetEvent
0x18002f274  test    eax, eax
0x18002f276  jz      loc_18002F3F6
0x18002f27c  mov     rcx, [rbx+48h]; hEvent
0x18002f280  call    cs:__imp_SetEvent
0x18002f286  test    eax, eax
0x18002f288  jz      loc_18002F392
0x18002f28e  jmp     loc_18002F346
0x18002f293  lea     rax, aNon; "Non"
0x18002f29a  mov     [rsp+1A0h+var_178], rdi
0x18002f29f  mov     r8d, 7Bh ; '{'
0x18002f2a5  lea     rcx, word_1800D7582
0x18002f2ac  test    sil, sil
0x18002f2af  lea     r9, aCrmnotificatio_4; "CrmNotificationTypeActivityWindowOpen %"...
0x18002f2b6  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::Service::Cr"...
0x18002f2bd  cmovz   rcx, rax
0x18002f2c1  mov     [rsp+1A0h+var_180], rcx
0x18002f2c6  lea     ecx, [r8-78h]
0x18002f2ca  call    AslLogCallPrintf
0x18002f2cf  test    sil, sil
0x18002f2d2  jz      short loc_18002F2FA
0x18002f2d4  mov     rcx, [rbx+30h]; hEvent
0x18002f2d8  call    cs:__imp_SetEvent
0x18002f2de  test    eax, eax
0x18002f2e0  jz      loc_18002F40F
0x18002f2e6  mov     rcx, [rbx+40h]; hEvent
0x18002f2ea  call    cs:__imp_ResetEvent
0x18002f2f0  test    eax, eax
0x18002f2f2  jz      loc_18002F3AB
0x18002f2f8  jmp     short loc_18002F346
0x18002f2fa  mov     rcx, [rbx+38h]; hEvent
0x18002f2fe  call    cs:__imp_SetEvent
0x18002f304  test    eax, eax
0x18002f306  jz      short loc_18002F360
0x18002f308  mov     rcx, [rbx+48h]; hEvent
0x18002f30c  call    cs:__imp_ResetEvent
0x18002f312  test    eax, eax
0x18002f314  jz      loc_18002F3C4
0x18002f31a  jmp     short loc_18002F346
0x18002f31c  mov     r8d, 71h ; 'q'
0x18002f322  mov     dword ptr [rsp+1A0h+var_178], 8000FFFFh
0x18002f32a  mov     [rsp+1A0h+var_180], rdi
0x18002f32f  lea     r9, aUnknownCrmActi; "Unknown CRM activity %p: [%#x]"
0x18002f336  lea     ecx, [r8-70h]
0x18002f33a  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::Service::Cr"...
0x18002f341  call    AslLogCallPrintf
0x18002f346  mov     rcx, [rbp+0A0h+var_30]
0x18002f34a  xor     rcx, rsp; StackCookie
0x18002f34d  call    __security_check_cookie
0x18002f352  add     rsp, 180h
0x18002f359  pop     r12
0x18002f35b  pop     rdi
0x18002f35c  pop     rsi
0x18002f35d  pop     rbx
0x18002f35e  pop     rbp
0x18002f35f  retn
0x18002f360  mov     rcx, [rbp+0A8h]; this
0x18002f367  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f36e  mov     edx, 0A01h; void *
0x18002f373  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f379  mov     rcx, [rbp+0A8h]; this
0x18002f380  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f387  mov     edx, 0A01h; void *
0x18002f38c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f392  mov     rcx, [rbp+0A8h]; this
0x18002f399  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f3a0  mov     edx, 0A01h; void *
0x18002f3a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f3ab  mov     rcx, [rbp+0A8h]; this
0x18002f3b2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f3b9  mov     edx, 0A06h; void *
0x18002f3be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f3c4  mov     rcx, [rbp+0A8h]; this
0x18002f3cb  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f3d2  mov     edx, 0A06h; void *
0x18002f3d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f3dd  mov     rcx, [rbp+0A8h]; this
0x18002f3e4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f3eb  mov     edx, 0A06h; void *
0x18002f3f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f3f6  mov     rcx, [rbp+0A8h]; this
0x18002f3fd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f404  mov     edx, 0A06h; void *
0x18002f409  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f40f  mov     rcx, [rbp+0A8h]; this
0x18002f416  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f41d  mov     edx, 0A01h; void *
0x18002f422  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
