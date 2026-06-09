# DdmThreadPool::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,ulong)

- ea: `0x180049aa0`
- end: `0x180049c3e`
- name: `?QueueWorkItem@DdmThreadPool@@UEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1K@Z`
- size: `414`
- prototype: `unsigned int(DdmThreadPool *__hidden this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007c0c`
- `0x180049aa0`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x180049b5a`
- `KERNEL32!CreateThreadpoolWork` at `0x180049b5a`
- `KERNEL32!SubmitThreadpoolWork` at `0x180049c03`
- `KERNEL32!SubmitThreadpoolWork` at `0x180049c03`
- `KERNEL32!CloseThreadpoolWork` at `0x180049c12`
- `KERNEL32!CloseThreadpoolWork` at `0x180049c12`
- `KERNEL32!GetLastError` at `0x180049b72`
- `KERNEL32!GetLastError` at `0x180049b72`

## string_xrefs

- `0x180049af9`: `DdmThreadPool::QueueWorkItem() called when helper is not initialized`
- `0x180049b92`: `DdmThreadPool::QueueWorkItem() CreateThreadpoolWork failed with error = %!WINERROR!`

## pseudocode

```c
__int64 __fastcall DdmThreadPool::QueueWorkItem(
        DdmThreadPool *this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *),
        void *a3)
{
  __int64 v6; // r8
  __int64 v7; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v10; // rbx
  DWORD LastError; // eax
  DWORD v12; // ebx
  __int64 v13; // r8
  __int64 v14; // rax
  _BYTE v15[16]; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-C0h]
  int v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+4Ch] [rbp-B4h]
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( *((_DWORD *)this + 24) )
  {
    ThreadpoolWork = CreateThreadpoolWork(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 24));
    v10 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v10);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(
          &v19,
          L"DdmThreadPool::QueueWorkItem() CreateThreadpoolWork failed with error = %!WINERROR!",
          LastError);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)&v20[2 * v14 - 4] );
          v18 = 0;
          v17 = 2 * v14 + 2;
          v16 = (const wchar_t *)&v19;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v13, 2, v15);
        }
      }
      return v12;
    }
  }
  else
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( aDdmthreadpoolQ_0[v7] );
      v16 = L"DdmThreadPool::QueueWorkItem() called when helper is not initialized";
      v17 = 2 * v7 + 2;
      v18 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v6, 2, v15);
    }
    return 4317;
  }
}

```

## disassembly

```asm
0x180049aa0  push    rbp
0x180049aa2  push    rbx
0x180049aa3  push    rsi
0x180049aa4  push    rdi
0x180049aa5  push    r14
0x180049aa7  lea     rbp, [rsp-760h]
0x180049aaf  sub     rsp, 860h
0x180049ab6  mov     rax, cs:__security_cookie
0x180049abd  xor     rax, rsp
0x180049ac0  mov     [rbp+780h+var_30], rax
0x180049ac7  mov     rsi, r8
0x180049aca  mov     rdi, rdx
0x180049acd  mov     rbx, rcx
0x180049ad0  xor     r14d, r14d
0x180049ad3  xor     edx, edx; Val
0x180049ad5  mov     [rsp+880h+var_830], r14d
0x180049ada  mov     r8d, 7FCh; Size
0x180049ae0  lea     rcx, [rsp+880h+var_82C]; void *
0x180049ae5  call    memset_0
0x180049aea  cmp     [rbx+60h], r14d
0x180049aee  jnz     short loc_180049B50
0x180049af0  test    cs:byte_1800CF404, 10h
0x180049af7  jz      short loc_180049B46
0x180049af9  lea     rcx, aDdmthreadpoolQ_0; "DdmThreadPool::QueueWorkItem() called w"...
0x180049b00  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049b04  inc     rax
0x180049b07  cmp     [rcx+rax*2], r14w
0x180049b0c  jnz     short loc_180049B04
0x180049b0e  lea     eax, ds:2[rax*2]
0x180049b15  mov     [rsp+880h+var_840], rcx
0x180049b1a  mov     [rsp+880h+var_838], eax
0x180049b1e  lea     rdx, RasDdmTraceInfo
0x180049b25  lea     rax, [rsp+880h+var_850]
0x180049b2a  mov     [rsp+880h+var_834], r14d
0x180049b2f  mov     r9d, 2
0x180049b35  mov     [rsp+880h+var_860], rax
0x180049b3a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049b41  call    McGenEventWrite_EventWriteTransfer
0x180049b46  mov     eax, 10DDh
0x180049b4b  jmp     loc_180049C20
0x180049b50  lea     r8, [rbx+18h]; pcbe
0x180049b54  mov     rdx, rsi; pv
0x180049b57  mov     rcx, rdi; pfnwk
0x180049b5a  call    cs:__imp_CreateThreadpoolWork
0x180049b61  nop     dword ptr [rax+rax+00h]
0x180049b66  mov     rbx, rax
0x180049b69  test    rax, rax
0x180049b6c  jnz     loc_180049C00
0x180049b72  call    cs:__imp_GetLastError
0x180049b79  nop     dword ptr [rax+rax+00h]
0x180049b7e  test    cs:byte_1800CF404, 8
0x180049b85  mov     ebx, eax
0x180049b87  jz      short loc_180049BFC
0x180049b89  mov     r8d, eax
0x180049b8c  mov     word ptr [rsp+880h+var_830], r14w
0x180049b92  lea     rdx, aDdmthreadpoolQ; "DdmThreadPool::QueueWorkItem() CreateTh"...
0x180049b99  lea     rcx, [rsp+880h+var_830]
0x180049b9e  call    FormatRRASErrorString
0x180049ba3  test    cs:byte_1800CF404, 8
0x180049baa  jz      short loc_180049BFC
0x180049bac  lea     rcx, [rsp+880h+var_830]
0x180049bb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049bb5  inc     rax
0x180049bb8  cmp     [rcx+rax*2], r14w
0x180049bbd  jnz     short loc_180049BB5
0x180049bbf  lea     eax, ds:2[rax*2]
0x180049bc6  mov     [rsp+880h+var_834], r14d
0x180049bcb  lea     rcx, [rsp+880h+var_830]
0x180049bd0  mov     [rsp+880h+var_838], eax
0x180049bd4  lea     rax, [rsp+880h+var_850]
0x180049bd9  mov     [rsp+880h+var_840], rcx
0x180049bde  mov     r9d, 2
0x180049be4  mov     [rsp+880h+var_860], rax
0x180049be9  lea     rdx, RasDdmTraceError
0x180049bf0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049bf7  call    McGenEventWrite_EventWriteTransfer
0x180049bfc  mov     eax, ebx
0x180049bfe  jmp     short loc_180049C20
0x180049c00  mov     rcx, rbx; pwk
0x180049c03  call    cs:__imp_SubmitThreadpoolWork
0x180049c0a  nop     dword ptr [rax+rax+00h]
0x180049c0f  mov     rcx, rbx; pwk
0x180049c12  call    cs:__imp_CloseThreadpoolWork
0x180049c19  nop     dword ptr [rax+rax+00h]
0x180049c1e  xor     eax, eax
0x180049c20  mov     rcx, [rbp+780h+var_30]
0x180049c27  xor     rcx, rsp; StackCookie
0x180049c2a  call    __security_check_cookie
0x180049c2f  add     rsp, 860h
0x180049c36  pop     r14
0x180049c38  pop     rdi
0x180049c39  pop     rsi
0x180049c3a  pop     rbx
0x180049c3b  pop     rbp
0x180049c3c  retn
```
