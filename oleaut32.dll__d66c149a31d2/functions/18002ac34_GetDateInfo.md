# GetDateInfo

- ea: `0x18002ac34`
- end: `0x18002adbf`
- name: `GetDateInfo`
- size: `395`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180027ef0`
- `0x18002a8c0`
- `0x18002bc1c`
- `0x180036a40`
- `0x180036cdc`
- `0x180047460`
- `0x180077f60`
- `0x180078010`

## callees

- `0x1800039b8`
- `0x180025ce0`
- `0x18002ac34`
- `0x18002adc8`
- `0x180048bf8`
- `0x18004a8f4`
- `0x18004d924`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002ac78`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002ac78`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002ad2e`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002ad2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ac91`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ad4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ac91`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ad4a`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18002ad0b`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18002ad0b`

## pseudocode

```c
__int64 __fastcall GetDateInfo(LCID a1, int a2, struct CDateInfo **a3)
{
  char *v3; // rdi
  LCID UserDefaultLCID; // eax
  unsigned int v8; // r15d
  LPVOID Value; // r14
  char **v10; // rsi
  unsigned __int64 v11; // rdx
  int inited; // ebx
  int v14; // ebx
  unsigned __int64 v15; // rdx
  CDateInfo *v16; // rcx
  struct CDateInfo *v17; // rcx
  char *v18; // [rsp+60h] [rbp+18h] BYREF
  struct CDateInfo *v19; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  *a3 = 0;
  v18 = 0;
  if ( g_bPerUserNlsCache )
  {
    GetUserInfo(&v18);
    v3 = v18;
  }
  if ( a1 == 1024 )
  {
    UserDefaultLCID = GetUserDefaultLCID();
LABEL_5:
    a1 = UserDefaultLCID;
    goto LABEL_6;
  }
  if ( a1 == 2048 )
  {
    UserDefaultLCID = GetSystemDefaultLCID();
    goto LABEL_5;
  }
LABEL_6:
  v8 = g_dwProcessNlsFlags | a2 & 0xFFFFFFF7;
  Value = TlsGetValue(g_itlsAppData);
  if ( !Value )
  {
    inited = InitAppData();
    if ( inited < 0 )
    {
LABEL_12:
      if ( v3 )
        operator delete(v3, v11);
      return (unsigned int)inited;
    }
    Value = TlsGetValue(g_itlsAppData);
  }
  v10 = (char **)*((_QWORD *)Value + 50);
  v19 = (struct CDateInfo *)v10;
  if ( !v10
    || *((_DWORD *)v10 + 4) != a1
    || *((_DWORD *)v10 + 5) != v8
    || v3 && !(unsigned int)IsSameUser(v3, v10[1])
    || (v14 = *(_DWORD *)v10, v14 != (unsigned int)NlsGetCacheUpdateCount()) )
  {
    inited = CDateInfo::Create(a1, v8, &v19, &v18);
    if ( inited >= 0 )
    {
      v16 = (CDateInfo *)*((_QWORD *)Value + 50);
      if ( v16 )
        CDateInfo::Release(v16);
      v17 = v19;
      *((_QWORD *)Value + 50) = v19;
      *a3 = v17;
    }
    v3 = v18;
    goto LABEL_12;
  }
  if ( v3 )
    operator delete(v3, v15);
  *a3 = (struct CDateInfo *)v10;
  return 0;
}

```

## disassembly

```asm
0x18002ac34  mov     [rsp+arg_0], rbx
0x18002ac39  mov     [rsp+arg_8], rbp
0x18002ac3e  push    rsi
0x18002ac3f  push    rdi
0x18002ac40  push    r12
0x18002ac42  push    r14
0x18002ac44  push    r15
0x18002ac46  sub     rsp, 20h
0x18002ac4a  xor     edi, edi
0x18002ac4c  mov     qword ptr [r8], 0
0x18002ac53  cmp     cs:?g_bPerUserNlsCache@@3KA, edi; ulong g_bPerUserNlsCache
0x18002ac59  mov     r12, r8
0x18002ac5c  mov     r15d, edx
0x18002ac5f  mov     [rsp+48h+arg_10], rdi
0x18002ac64  mov     ebp, ecx
0x18002ac66  jnz     loc_18002AD58
0x18002ac6c  cmp     ebp, 400h
0x18002ac72  jnz     loc_18002AD22
0x18002ac78  call    cs:__imp_GetUserDefaultLCID
0x18002ac7e  mov     ebp, eax
0x18002ac80  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18002ac86  and     r15d, 0FFFFFFF7h
0x18002ac8a  or      r15d, cs:?g_dwProcessNlsFlags@@3KA; ulong g_dwProcessNlsFlags
0x18002ac91  call    cs:__imp_TlsGetValue
0x18002ac97  mov     r14, rax
0x18002ac9a  test    rax, rax
0x18002ac9d  jz      loc_18002AD39
0x18002aca3  mov     rsi, [r14+190h]
0x18002acaa  mov     [rsp+48h+arg_18], rsi
0x18002acaf  test    rsi, rsi
0x18002acb2  jz      short loc_18002ACBF
0x18002acb4  cmp     [rsi+10h], ebp
0x18002acb7  jnz     short loc_18002ACBF
0x18002acb9  cmp     [rsi+14h], r15d
0x18002acbd  jz      short loc_18002AD04
0x18002acbf  lea     r9, [rsp+48h+arg_10]; char **
0x18002acc4  mov     edx, r15d; unsigned int
0x18002acc7  lea     r8, [rsp+48h+arg_18]; struct CDateInfo **
0x18002accc  mov     ecx, ebp; unsigned int
0x18002acce  call    ?Create@CDateInfo@@SAJKKPEAPEAV1@PEAPEAD@Z; CDateInfo::Create(ulong,ulong,CDateInfo * *,char * *)
0x18002acd3  mov     ebx, eax
0x18002acd5  test    eax, eax
0x18002acd7  jns     loc_18002AD8C
0x18002acdd  mov     rdi, [rsp+48h+arg_10]
0x18002ace2  test    rdi, rdi
0x18002ace5  jnz     loc_18002ADB2
0x18002aceb  mov     eax, ebx
0x18002aced  mov     rbx, [rsp+48h+arg_0]
0x18002acf2  mov     rbp, [rsp+48h+arg_8]
0x18002acf7  add     rsp, 20h
0x18002acfb  pop     r15
0x18002acfd  pop     r14
0x18002acff  pop     r12
0x18002ad01  pop     rdi
0x18002ad02  pop     rsi
0x18002ad03  retn
0x18002ad04  test    rdi, rdi
0x18002ad07  jnz     short loc_18002AD6C
0x18002ad09  mov     ebx, [rsi]
0x18002ad0b  call    cs:__imp_NlsGetCacheUpdateCount
0x18002ad11  cmp     ebx, eax
0x18002ad13  jnz     short loc_18002ACBF
0x18002ad15  test    rdi, rdi
0x18002ad18  jnz     short loc_18002AD82
0x18002ad1a  mov     [r12], rsi
0x18002ad1e  xor     eax, eax
0x18002ad20  jmp     short loc_18002ACED
0x18002ad22  cmp     ebp, 800h
0x18002ad28  jnz     loc_18002AC80
0x18002ad2e  call    cs:__imp_GetSystemDefaultLCID
0x18002ad34  jmp     loc_18002AC7E
0x18002ad39  call    InitAppData
0x18002ad3e  mov     ebx, eax
0x18002ad40  test    eax, eax
0x18002ad42  js      short loc_18002ACE2
0x18002ad44  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18002ad4a  call    cs:__imp_TlsGetValue
0x18002ad50  mov     r14, rax
0x18002ad53  jmp     loc_18002ACA3
0x18002ad58  lea     rcx, [rsp+48h+arg_10]; char **
0x18002ad5d  call    ?GetUserInfo@@YAXPEAPEAD@Z; GetUserInfo(char * *)
0x18002ad62  mov     rdi, [rsp+48h+arg_10]
0x18002ad67  jmp     loc_18002AC6C
0x18002ad6c  mov     rdx, [rsi+8]; char *
0x18002ad70  mov     rcx, rdi; char *
0x18002ad73  call    ?IsSameUser@@YAHPEAD0@Z; IsSameUser(char *,char *)
0x18002ad78  test    eax, eax
0x18002ad7a  jz      loc_18002ACBF
0x18002ad80  jmp     short loc_18002AD09
0x18002ad82  mov     rcx, rdi; void *
0x18002ad85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ad8a  jmp     short loc_18002AD1A
0x18002ad8c  mov     rcx, [r14+190h]; this
0x18002ad93  test    rcx, rcx
0x18002ad96  jz      short loc_18002AD9D
0x18002ad98  call    ?Release@CDateInfo@@QEAAKXZ; CDateInfo::Release(void)
0x18002ad9d  mov     rcx, [rsp+48h+arg_18]
0x18002ada2  mov     [r14+190h], rcx
0x18002ada9  mov     [r12], rcx
0x18002adad  jmp     loc_18002ACDD
0x18002adb2  mov     rcx, rdi; void *
0x18002adb5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002adba  jmp     loc_18002ACEB
```
