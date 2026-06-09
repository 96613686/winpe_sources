# HrFormatTaskDlgMessage(HINSTANCE__ * const,uint,uint,ushort * *,ushort * *,ushort * *)

- ea: `0x18001e7c4`
- end: `0x18001e9a6`
- name: `?HrFormatTaskDlgMessage@@YAJQEAUHINSTANCE__@@IIPEAPEAG11@Z`
- size: `482`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, unsigned int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e564`

## callees

- `0x180002270`
- `0x180010e9c`
- `0x180012458`
- `0x18001e7c4`
- `0x18001e9ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e898`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e8bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e898`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e8bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e94e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e94e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e8d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e90c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e8d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e90c`

## pseudocode

```c
__int64 __fastcall HrFormatTaskDlgMessage(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        LPVOID *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  HINSTANCE v7; // r14
  int SvcDispNameAndDesc; // eax
  void *v10; // r12
  int v11; // ebx
  struct _SERVICE_DESCRIPTIONW *v12; // r13
  int StringW; // ebx
  int v14; // r14d
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  int Error; // eax
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  struct _SERVICE_DESCRIPTIONW *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v25[256]; // [rsp+250h] [rbp+150h] BYREF

  if ( a4 && a5 && a6 )
  {
    v7 = g_hinst;
    if ( !g_hinst )
      return 2147942487LL;
    *a4 = 0;
    *a5 = 0;
    *a6 = 0;
    pv = 0;
    v23 = 0;
    v20 = 0;
    v21 = 0;
    SvcDispNameAndDesc = HrGetSvcDispNameAndDesc(a1, &pv, &v20, (LPVOID *)&v23, &v21);
    v10 = pv;
    v11 = SvcDispNameAndDesc;
    v12 = v23;
    if ( SvcDispNameAndDesc < 0 )
      goto LABEL_18;
    *a4 = pv;
    StringW = LoadStringW(v7, 0x37u, Buffer, 256);
    if ( StringW && (v14 = LoadStringW(v7, 0x38u, v25, 256)) != 0 )
    {
      v15 = (int)(StringW + v20);
      v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
      *a5 = v16;
      if ( !v16 )
      {
        v11 = -2147024882;
        goto LABEL_18;
      }
      v11 = StringCchPrintfW(v16, v15, Buffer, v10);
      if ( v11 < 0 )
      {
LABEL_18:
        CoTaskMemFree(v10);
        CoTaskMemFree(*a5);
        CoTaskMemFree(*a6);
        *a4 = 0;
        *a5 = 0;
        *a6 = 0;
        goto LABEL_19;
      }
      v17 = (int)(v14 + v21);
      v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17);
      *a6 = v18;
      if ( !v18 )
      {
        v11 = -2147024882;
        goto LABEL_17;
      }
      Error = StringCchPrintfW(v18, v17, v25, v12->lpDescription);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    v11 = Error;
LABEL_17:
    if ( v11 >= 0 )
    {
LABEL_19:
      CoTaskMemFree(v12);
      return (unsigned int)v11;
    }
    goto LABEL_18;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001e7c4  push    rbp
0x18001e7c6  push    rbx
0x18001e7c7  push    rsi
0x18001e7c8  push    rdi
0x18001e7c9  push    r12
0x18001e7cb  push    r13
0x18001e7cd  push    r14
0x18001e7cf  push    r15
0x18001e7d1  lea     rbp, [rsp-368h]
0x18001e7d9  sub     rsp, 468h
0x18001e7e0  mov     rax, cs:__security_cookie
0x18001e7e7  xor     rax, rsp
0x18001e7ea  mov     [rbp+3A0h+var_50], rax
0x18001e7f1  mov     rsi, [rbp+3A0h+arg_20]
0x18001e7f8  xor     eax, eax
0x18001e7fa  mov     rdi, [rbp+3A0h+arg_28]
0x18001e801  mov     r15, r9
0x18001e804  test    r9, r9
0x18001e807  jz      loc_18001E97E
0x18001e80d  test    rsi, rsi
0x18001e810  jz      loc_18001E97E
0x18001e816  test    rdi, rdi
0x18001e819  jz      loc_18001E97E
0x18001e81f  mov     r14, cs:g_hinst
0x18001e826  test    r14, r14
0x18001e829  jnz     short loc_18001E835
0x18001e82b  mov     eax, 80070057h
0x18001e830  jmp     loc_18001E983
0x18001e835  mov     [r9], rax
0x18001e838  lea     r8, [rsp+4A0h+var_470]; unsigned int *
0x18001e83d  mov     [rsi], rax
0x18001e840  lea     r9, [rsp+4A0h+var_460]; struct _SERVICE_DESCRIPTIONW **
0x18001e845  mov     [rdi], rax
0x18001e848  lea     rdx, [rsp+4A0h+pv]; unsigned __int16 **
0x18001e84d  mov     [rsp+4A0h+pv], rax
0x18001e852  mov     [rsp+4A0h+var_460], rax
0x18001e857  mov     [rsp+4A0h+var_470], eax
0x18001e85b  mov     [rsp+4A0h+var_46C], eax
0x18001e85f  lea     rax, [rsp+4A0h+var_46C]
0x18001e864  mov     [rsp+4A0h+var_480], rax; unsigned int *
0x18001e869  call    ?HrGetSvcDispNameAndDesc@@YAJQEAGPEAPEAGPEAKPEAPEAU_SERVICE_DESCRIPTIONW@@2@Z; HrGetSvcDispNameAndDesc(ushort * const,ushort * *,ulong *,_SERVICE_DESCRIPTIONW * *,ulong *)
0x18001e86e  mov     r12, [rsp+4A0h+pv]
0x18001e873  mov     ebx, eax
0x18001e875  mov     r13, [rsp+4A0h+var_460]
0x18001e87a  test    eax, eax
0x18001e87c  js      loc_18001E94B
0x18001e882  mov     r9d, 100h; cchBufferMax
0x18001e888  mov     [r15], r12
0x18001e88b  lea     r8, [rsp+4A0h+Buffer]; lpBuffer
0x18001e890  mov     edx, 37h ; '7'; uID
0x18001e895  mov     rcx, r14; hInstance
0x18001e898  call    cs:__imp_LoadStringW
0x18001e89e  mov     ebx, eax
0x18001e8a0  test    eax, eax
0x18001e8a2  jz      loc_18001E940
0x18001e8a8  mov     r9d, 100h; cchBufferMax
0x18001e8ae  lea     r8, [rbp+3A0h+var_250]; lpBuffer
0x18001e8b5  mov     edx, 38h ; '8'; uID
0x18001e8ba  mov     rcx, r14; hInstance
0x18001e8bd  call    cs:__imp_LoadStringW
0x18001e8c3  mov     r14d, eax
0x18001e8c6  test    eax, eax
0x18001e8c8  jz      short loc_18001E940
0x18001e8ca  mov     edx, [rsp+4A0h+var_470]
0x18001e8ce  add     edx, ebx
0x18001e8d0  movsxd  rbx, edx
0x18001e8d3  lea     rcx, [rbx+rbx]; cb
0x18001e8d7  call    cs:__imp_CoTaskMemAlloc
0x18001e8dd  mov     [rsi], rax
0x18001e8e0  test    rax, rax
0x18001e8e3  jz      short loc_18001E939
0x18001e8e5  mov     r9, r12
0x18001e8e8  lea     r8, [rsp+4A0h+Buffer]; unsigned __int16 *
0x18001e8ed  mov     rdx, rbx; unsigned __int64
0x18001e8f0  mov     rcx, rax; unsigned __int16 *
0x18001e8f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e8f8  mov     ebx, eax
0x18001e8fa  test    eax, eax
0x18001e8fc  js      short loc_18001E94B
0x18001e8fe  mov     ecx, [rsp+4A0h+var_46C]
0x18001e902  add     ecx, r14d
0x18001e905  movsxd  rbx, ecx
0x18001e908  lea     rcx, [rbx+rbx]; cb
0x18001e90c  call    cs:__imp_CoTaskMemAlloc
0x18001e912  mov     [rdi], rax
0x18001e915  test    rax, rax
0x18001e918  jz      short loc_18001E932
0x18001e91a  mov     r9, [r13+0]
0x18001e91e  lea     r8, [rbp+3A0h+var_250]; unsigned __int16 *
0x18001e925  mov     rdx, rbx; unsigned __int64
0x18001e928  mov     rcx, rax; unsigned __int16 *
0x18001e92b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e930  jmp     short loc_18001E945
0x18001e932  mov     ebx, 8007000Eh
0x18001e937  jmp     short loc_18001E947
0x18001e939  mov     ebx, 8007000Eh
0x18001e93e  jmp     short loc_18001E94B
0x18001e940  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e945  mov     ebx, eax
0x18001e947  test    ebx, ebx
0x18001e949  jns     short loc_18001E971
0x18001e94b  mov     rcx, r12; pv
0x18001e94e  call    cs:__imp_CoTaskMemFree
0x18001e954  mov     rcx, [rsi]; pv
0x18001e957  call    cs:__imp_CoTaskMemFree
0x18001e95d  mov     rcx, [rdi]; pv
0x18001e960  call    cs:__imp_CoTaskMemFree
0x18001e966  xor     eax, eax
0x18001e968  mov     [r15], rax
0x18001e96b  mov     [rsi], rax
0x18001e96e  mov     [rdi], rax
0x18001e971  mov     rcx, r13; pv
0x18001e974  call    cs:__imp_CoTaskMemFree
0x18001e97a  mov     eax, ebx
0x18001e97c  jmp     short loc_18001E983
0x18001e97e  mov     eax, 80004003h
0x18001e983  mov     rcx, [rbp+3A0h+var_50]
0x18001e98a  xor     rcx, rsp; StackCookie
0x18001e98d  call    __security_check_cookie
0x18001e992  add     rsp, 468h
0x18001e999  pop     r15
0x18001e99b  pop     r14
0x18001e99d  pop     r13
0x18001e99f  pop     r12
0x18001e9a1  pop     rdi
0x18001e9a2  pop     rsi
0x18001e9a3  pop     rbx
0x18001e9a4  pop     rbp
0x18001e9a5  retn
```
