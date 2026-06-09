# DdmThreadPool::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,ulong)

- ea: `0x180048830`
- end: `0x18004899e`
- name: `?QueueWorkItem@DdmThreadPool@@UEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1K@Z`
- size: `366`
- prototype: `unsigned int(DdmThreadPool *__hidden this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007b7c`
- `0x180048830`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x1800488d3`
- `KERNEL32!CreateThreadpoolWork` at `0x1800488d3`
- `KERNEL32!SubmitThreadpoolWork` at `0x180048970`
- `KERNEL32!SubmitThreadpoolWork` at `0x180048970`
- `KERNEL32!CloseThreadpoolWork` at `0x180048979`
- `KERNEL32!CloseThreadpoolWork` at `0x180048979`
- `KERNEL32!GetLastError` at `0x1800488e5`
- `KERNEL32!GetLastError` at `0x1800488e5`

## string_xrefs

- `0x180048889`: `DdmThreadPool::QueueWorkItem() called when helper is not initialized`
- `0x1800488ff`: `DdmThreadPool::QueueWorkItem() CreateThreadpoolWork failed with error = %!WINERROR!`

## pseudocode

```c
__int64 __fastcall DdmThreadPool::QueueWorkItem(
        DdmThreadPool *this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *),
        void *a3)
{
  __int64 v6; // r8
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v9; // rbx
  DWORD LastError; // eax
  DWORD v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rax
  _BYTE v14[16]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( *((_DWORD *)this + 24) )
  {
    ThreadpoolWork = CreateThreadpoolWork(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 24));
    v9 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v9);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(
          &v17,
          L"DdmThreadPool::QueueWorkItem() CreateThreadpoolWork failed with error = %!WINERROR!",
          LastError);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&v18[2 * v13 - 4] );
          v16 = (unsigned int)(2 * v13 + 2);
          v15 = (const wchar_t *)&v17;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v12, 2, v14);
        }
      }
      return v11;
    }
  }
  else
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v16 = 138;
      v15 = L"DdmThreadPool::QueueWorkItem() called when helper is not initialized";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v6, 2, v14);
    }
    return 4317;
  }
}

```

## disassembly

```asm
0x180048830  push    rbp
0x180048832  push    rbx
0x180048833  push    rsi
0x180048834  push    rdi
0x180048835  push    r14
0x180048837  lea     rbp, [rsp-770h]
0x18004883f  sub     rsp, 870h
0x180048846  mov     rax, cs:__security_cookie
0x18004884d  xor     rax, rsp
0x180048850  mov     [rbp+790h+var_30], rax
0x180048857  mov     rsi, r8
0x18004885a  mov     rdi, rdx
0x18004885d  mov     rbx, rcx
0x180048860  xor     r14d, r14d
0x180048863  xor     edx, edx; Val
0x180048865  mov     [rsp+890h+var_830], r14d
0x18004886a  mov     r8d, 7FCh; Size
0x180048870  lea     rcx, [rsp+890h+var_82C]; void *
0x180048875  call    memset_0
0x18004887a  cmp     [rbx+60h], r14d
0x18004887e  jnz     short loc_1800488C9
0x180048880  test    cs:byte_1800C8404, 10h
0x180048887  jz      short loc_1800488BF
0x180048889  lea     rax, aDdmthreadpoolQ_0; "DdmThreadPool::QueueWorkItem() called w"...
0x180048890  mov     [rsp+890h+var_840], 8Ah
0x180048899  mov     [rsp+890h+var_848], rax
0x18004889e  lea     r9d, [r14+2]
0x1800488a2  lea     rax, [rsp+890h+var_858]
0x1800488a7  lea     rdx, RasDdmTraceInfo
0x1800488ae  mov     [rsp+890h+var_870], rax
0x1800488b3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800488ba  call    McGenEventWrite_EventWriteTransfer
0x1800488bf  mov     eax, 10DDh
0x1800488c4  jmp     loc_180048981
0x1800488c9  lea     r8, [rbx+18h]; pcbe
0x1800488cd  mov     rdx, rsi; pv
0x1800488d0  mov     rcx, rdi; pfnwk
0x1800488d3  call    cs:__imp_CreateThreadpoolWork
0x1800488d9  mov     rbx, rax
0x1800488dc  test    rax, rax
0x1800488df  jnz     loc_18004896D
0x1800488e5  call    cs:__imp_GetLastError
0x1800488eb  test    cs:byte_1800C8404, 8
0x1800488f2  mov     ebx, eax
0x1800488f4  jz      short loc_180048969
0x1800488f6  mov     r8d, eax
0x1800488f9  mov     word ptr [rsp+890h+var_830], r14w
0x1800488ff  lea     rdx, aDdmthreadpoolQ; "DdmThreadPool::QueueWorkItem() CreateTh"...
0x180048906  lea     rcx, [rsp+890h+var_830]
0x18004890b  call    FormatRRASErrorString
0x180048910  test    cs:byte_1800C8404, 8
0x180048917  jz      short loc_180048969
0x180048919  lea     rcx, [rsp+890h+var_830]
0x18004891e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048922  inc     rax
0x180048925  cmp     [rcx+rax*2], r14w
0x18004892a  jnz     short loc_180048922
0x18004892c  lea     eax, ds:2[rax*2]
0x180048933  mov     dword ptr [rsp+890h+var_840+4], r14d
0x180048938  lea     rcx, [rsp+890h+var_830]
0x18004893d  mov     dword ptr [rsp+890h+var_840], eax
0x180048941  lea     rax, [rsp+890h+var_858]
0x180048946  mov     [rsp+890h+var_848], rcx
0x18004894b  mov     r9d, 2
0x180048951  mov     [rsp+890h+var_870], rax
0x180048956  lea     rdx, RasDdmTraceError
0x18004895d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048964  call    McGenEventWrite_EventWriteTransfer
0x180048969  mov     eax, ebx
0x18004896b  jmp     short loc_180048981
0x18004896d  mov     rcx, rbx; pwk
0x180048970  call    cs:__imp_SubmitThreadpoolWork
0x180048976  mov     rcx, rbx; pwk
0x180048979  call    cs:__imp_CloseThreadpoolWork
0x18004897f  xor     eax, eax
0x180048981  mov     rcx, [rbp+790h+var_30]
0x180048988  xor     rcx, rsp; StackCookie
0x18004898b  call    __security_check_cookie
0x180048990  add     rsp, 870h
0x180048997  pop     r14
0x180048999  pop     rdi
0x18004899a  pop     rsi
0x18004899b  pop     rbx
0x18004899c  pop     rbp
0x18004899d  retn
```
