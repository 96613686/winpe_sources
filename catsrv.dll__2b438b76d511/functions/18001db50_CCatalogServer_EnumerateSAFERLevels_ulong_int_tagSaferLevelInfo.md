# CCatalogServer::EnumerateSAFERLevels(ulong,int *,tagSaferLevelInfo * *)

- ea: `0x18001db50`
- end: `0x18001dd13`
- name: `?EnumerateSAFERLevels@CCatalogServer@@UEAAJKPEAHPEAPEAUtagSaferLevelInfo@@@Z`
- size: `451`
- prototype: `int(CCatalogServer *__hidden this, unsigned int, int *, struct tagSaferLevelInfo **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001db50`
- `0x18001deb0`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbf5`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x18001dc47`
- `api-ms-win-core-localization-l1-2-0!IsValidLocale` at `0x18001dc47`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001dc5c`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001dcea`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001dc5c`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18001dcea`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001dc51`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001dc51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dcf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dbab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dc28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dbab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dc28`
- `ADVAPI32!SaferGetPolicyInformation` at `0x18001db9c`
- `ADVAPI32!SaferGetPolicyInformation` at `0x18001dbe9`
- `ADVAPI32!SaferGetPolicyInformation` at `0x18001db9c`
- `ADVAPI32!SaferGetPolicyInformation` at `0x18001dbe9`

## pseudocode

```c
__int64 __fastcall CCatalogServer::EnumerateSAFERLevels(
        CCatalogServer *this,
        LCID a2,
        int *a3,
        struct tagSaferLevelInfo **a4)
{
  char *v4; // rdi
  DWORD v8; // ebx
  void *v9; // r14
  signed int SaferLevelName; // ebx
  LCID ThreadLocale; // r13d
  signed int v12; // esi
  signed int LastError; // eax
  SIZE_T v14; // rbx
  __int64 v15; // rbp
  CCatalogServer *v16; // rcx
  signed int v17; // ebp
  void *v18; // rcx
  BOOL v20; // [rsp+30h] [rbp-58h]
  SIZE_T cb; // [rsp+A0h] [rbp+18h] BYREF

  v4 = 0;
  LODWORD(cb) = 0;
  if ( a3 && a4 )
  {
    SaferGetPolicyInformation(1u, SaferPolicyLevelList, 0, 0, (PDWORD)&cb, 0);
    v8 = cb;
    v9 = CoTaskMemAlloc((unsigned int)cb);
    if ( !v9 )
      return (unsigned int)-2147024882;
    v20 = 0;
    ThreadLocale = 2048;
    if ( SaferGetPolicyInformation(1u, SaferPolicyLevelList, v8, v9, (PDWORD)&cb, 0) )
    {
      v14 = 16LL * ((unsigned int)cb >> 2);
      v12 = (unsigned int)cb >> 2;
      v4 = (char *)CoTaskMemAlloc(v14);
      if ( !v4 )
      {
        SaferLevelName = -2147024882;
LABEL_24:
        CoTaskMemFree(v9);
        return (unsigned int)SaferLevelName;
      }
      if ( IsValidLocale(a2, 1u) )
      {
        ThreadLocale = GetThreadLocale();
        v20 = SetThreadLocale(a2);
      }
      memset_0(v4, 0, v14);
      v15 = 0;
      if ( v12 )
      {
        while ( 1 )
        {
          v16 = (CCatalogServer *)(16LL * (unsigned int)v15);
          *(_DWORD *)((char *)v16 + (_QWORD)v4) = *((_DWORD *)v9 + v15);
          SaferLevelName = CCatalogServer::GetSaferLevelName(
                             v16,
                             *((_DWORD *)v9 + v15),
                             (unsigned __int16 **)&v4[(_QWORD)v16 + 8]);
          if ( SaferLevelName < 0 )
            goto LABEL_16;
          v15 = (unsigned int)(v15 + 1);
          if ( (int)v15 >= v12 )
            goto LABEL_15;
        }
      }
    }
    else
    {
      v12 = 0;
      LastError = GetLastError();
      SaferLevelName = LastError;
      if ( LastError > 0 )
        SaferLevelName = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
      if ( SaferLevelName < 0 )
      {
LABEL_16:
        if ( v4 )
        {
          v17 = 0;
          if ( v12 )
          {
            do
            {
              v18 = *(void **)&v4[16 * v17 + 8];
              if ( !v18 )
                break;
              CoTaskMemFree(v18);
              ++v17;
            }
            while ( v17 < v12 );
          }
          CoTaskMemFree(v4);
        }
        goto LABEL_22;
      }
    }
    *a3 = v12;
    SaferLevelName = 0;
    *a4 = (struct tagSaferLevelInfo *)v4;
LABEL_22:
    if ( v20 )
      SetThreadLocale(ThreadLocale);
    goto LABEL_24;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001db50  mov     rax, rsp
0x18001db53  push    rbx
0x18001db54  push    rbp
0x18001db55  push    rsi
0x18001db56  push    rdi
0x18001db57  push    r12
0x18001db59  push    r13
0x18001db5b  push    r14
0x18001db5d  push    r15
0x18001db5f  sub     rsp, 48h
0x18001db63  xor     edi, edi
0x18001db65  mov     r15, r9
0x18001db68  mov     [rax+18h], edi
0x18001db6b  mov     r12, r8
0x18001db6e  mov     ebp, edx
0x18001db70  test    r8, r8
0x18001db73  jz      loc_18001DCFD
0x18001db79  test    r9, r9
0x18001db7c  jz      loc_18001DCFD
0x18001db82  mov     [rax-60h], rdi
0x18001db86  lea     esi, [rdi+1]
0x18001db89  lea     rax, [rax+18h]
0x18001db8d  mov     edx, esi; SaferPolicyInfoClass
0x18001db8f  mov     ecx, esi; dwScopeId
0x18001db91  mov     [rsp+88h+InfoBufferRetSize], rax; InfoBufferRetSize
0x18001db96  xor     r9d, r9d; InfoBuffer
0x18001db99  xor     r8d, r8d; InfoBufferSize
0x18001db9c  call    cs:__imp_SaferGetPolicyInformation
0x18001dba2  mov     ebx, dword ptr [rsp+88h+cb]
0x18001dba9  mov     ecx, ebx; cb
0x18001dbab  call    cs:__imp_CoTaskMemAlloc
0x18001dbb1  mov     r14, rax
0x18001dbb4  test    rax, rax
0x18001dbb7  jnz     short loc_18001DBC3
0x18001dbb9  mov     ebx, 8007000Eh
0x18001dbbe  jmp     loc_18001DCF9
0x18001dbc3  lea     rax, [rsp+88h+cb]
0x18001dbcb  mov     [rsp+88h+lpReserved], rdi; lpReserved
0x18001dbd0  mov     r9, r14; InfoBuffer
0x18001dbd3  mov     [rsp+88h+InfoBufferRetSize], rax; InfoBufferRetSize
0x18001dbd8  mov     r8d, ebx; InfoBufferSize
0x18001dbdb  mov     [rsp+88h+var_58], edi
0x18001dbdf  mov     edx, esi; SaferPolicyInfoClass
0x18001dbe1  mov     ecx, esi; dwScopeId
0x18001dbe3  mov     r13d, 800h
0x18001dbe9  call    cs:__imp_SaferGetPolicyInformation
0x18001dbef  test    eax, eax
0x18001dbf1  jnz     short loc_18001DC13
0x18001dbf3  mov     esi, edi
0x18001dbf5  call    cs:__imp_GetLastError
0x18001dbfb  mov     ebx, eax
0x18001dbfd  test    eax, eax
0x18001dbff  jle     loc_18001DCA2
0x18001dc05  movzx   ebx, ax
0x18001dc08  or      ebx, 80070000h
0x18001dc0e  jmp     loc_18001DCA2
0x18001dc13  mov     eax, dword ptr [rsp+88h+cb]
0x18001dc1a  shr     eax, 2
0x18001dc1d  mov     ebx, eax
0x18001dc1f  shl     rbx, 4
0x18001dc23  mov     rcx, rbx; cb
0x18001dc26  mov     esi, eax
0x18001dc28  call    cs:__imp_CoTaskMemAlloc
0x18001dc2e  mov     rdi, rax
0x18001dc31  test    rax, rax
0x18001dc34  jnz     short loc_18001DC40
0x18001dc36  mov     ebx, 8007000Eh
0x18001dc3b  jmp     loc_18001DCF0
0x18001dc40  mov     edx, 1; dwFlags
0x18001dc45  mov     ecx, ebp; Locale
0x18001dc47  call    cs:__imp_IsValidLocale
0x18001dc4d  test    eax, eax
0x18001dc4f  jz      short loc_18001DC66
0x18001dc51  call    cs:__imp_GetThreadLocale
0x18001dc57  mov     ecx, ebp; Locale
0x18001dc59  mov     r13d, eax
0x18001dc5c  call    cs:__imp_SetThreadLocale
0x18001dc62  mov     [rsp+88h+var_58], eax
0x18001dc66  mov     r8, rbx; Size
0x18001dc69  xor     edx, edx; Val
0x18001dc6b  mov     rcx, rdi; void *
0x18001dc6e  call    memset_0
0x18001dc73  xor     ebp, ebp
0x18001dc75  test    esi, esi
0x18001dc77  jz      short loc_18001DCD7
0x18001dc79  mov     eax, [r14+rbp*4]
0x18001dc7d  lea     r8, [rdi+8]
0x18001dc81  mov     ecx, ebp
0x18001dc83  shl     rcx, 4; this
0x18001dc87  add     r8, rcx; unsigned __int16 **
0x18001dc8a  mov     [rdi+rcx], eax
0x18001dc8d  mov     edx, [r14+rbp*4]; unsigned int
0x18001dc91  call    ?GetSaferLevelName@CCatalogServer@@AEAAJKPEAPEAG@Z; CCatalogServer::GetSaferLevelName(ulong,ushort * *)
0x18001dc96  mov     ebx, eax
0x18001dc98  test    eax, eax
0x18001dc9a  js      short loc_18001DCA6
0x18001dc9c  inc     ebp
0x18001dc9e  cmp     ebp, esi
0x18001dca0  jl      short loc_18001DC79
0x18001dca2  test    ebx, ebx
0x18001dca4  jns     short loc_18001DCD7
0x18001dca6  test    rdi, rdi
0x18001dca9  jz      short loc_18001DCE0
0x18001dcab  xor     ebp, ebp
0x18001dcad  test    esi, esi
0x18001dcaf  jz      short loc_18001DCCC
0x18001dcb1  mov     eax, ebp
0x18001dcb3  add     rax, rax
0x18001dcb6  mov     rcx, [rdi+rax*8+8]; pv
0x18001dcbb  test    rcx, rcx
0x18001dcbe  jz      short loc_18001DCCC
0x18001dcc0  call    cs:__imp_CoTaskMemFree
0x18001dcc6  inc     ebp
0x18001dcc8  cmp     ebp, esi
0x18001dcca  jl      short loc_18001DCB1
0x18001dccc  mov     rcx, rdi; pv
0x18001dccf  call    cs:__imp_CoTaskMemFree
0x18001dcd5  jmp     short loc_18001DCE0
0x18001dcd7  mov     [r12], esi
0x18001dcdb  xor     ebx, ebx
0x18001dcdd  mov     [r15], rdi
0x18001dce0  cmp     [rsp+88h+var_58], 0
0x18001dce5  jz      short loc_18001DCF0
0x18001dce7  mov     ecx, r13d; Locale
0x18001dcea  call    cs:__imp_SetThreadLocale
0x18001dcf0  mov     rcx, r14; pv
0x18001dcf3  call    cs:__imp_CoTaskMemFree
0x18001dcf9  mov     eax, ebx
0x18001dcfb  jmp     short loc_18001DD02
0x18001dcfd  mov     eax, 80004003h
0x18001dd02  add     rsp, 48h
0x18001dd06  pop     r15
0x18001dd08  pop     r14
0x18001dd0a  pop     r13
0x18001dd0c  pop     r12
0x18001dd0e  pop     rdi
0x18001dd0f  pop     rsi
0x18001dd10  pop     rbp
0x18001dd11  pop     rbx
0x18001dd12  retn
```
