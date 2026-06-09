# CHTTPMailTransport::OpenRequest(void)

- ea: `0x1800a2e58`
- end: `0x1800a3003`
- name: `?OpenRequest@CHTTPMailTransport@@QEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800a3010`

## callees

- `0x18009ef3c`
- `0x1800a0da4`
- `0x1800a0f60`
- `0x1800a2e58`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a2fa5`
- `KERNEL32!GetLastError` at `0x1800a2fa5`
- `WININET!HttpOpenRequestA` at `0x1800a2f93`
- `WININET!HttpOpenRequestA` at `0x1800a2f93`
- `WININET!InternetSetOptionA` at `0x1800a2f0e`
- `WININET!InternetSetOptionA` at `0x1800a2f37`
- `WININET!InternetSetOptionA` at `0x1800a2f0e`
- `WININET!InternetSetOptionA` at `0x1800a2f37`

## pseudocode

```c
__int64 __fastcall CHTTPMailTransport::OpenRequest(DWORD_PTR dwContext)
{
  size_t *v1; // rdx
  size_t *v2; // r14
  size_t *v3; // rbp
  const CHAR *v5; // rcx
  int v6; // esi
  char *v7; // r9
  __int64 v8; // rdi
  __int64 v9; // r9
  const CHAR *v10; // rax
  HINTERNET v11; // rax
  char *lpszReferrer; // [rsp+20h] [rbp-48h]
  unsigned __int16 v14; // [rsp+70h] [rbp+8h] BYREF
  LPCSTR lpszServerName; // [rsp+78h] [rbp+10h] BYREF
  LPCSTR lpszObjectName; // [rsp+80h] [rbp+18h] BYREF

  lpszServerName = 0;
  v1 = (size_t *)(dwContext + 1208);
  v14 = 0;
  lpszObjectName = 0;
  v2 = (size_t *)&dword_1800D8644;
  v3 = (size_t *)&dword_1800D8644;
  if ( dwContext != -952 )
    v3 = (size_t *)(dwContext + 952);
  v5 = *(const CHAR **)(dwContext + 192);
  if ( v1 )
    v2 = v1;
  v6 = HrCrackUrl(v5, (char **)&lpszServerName, (char **)&lpszObjectName, &v14);
  if ( v6 >= 0 )
  {
    v6 = CHTTPMailTransport::HrConnectToHost(dwContext, lpszServerName, v14, v7, lpszReferrer);
    if ( v6 >= 0 )
    {
      v8 = -1;
      if ( v3 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *((_BYTE *)v3 + v9) );
      }
      else
      {
        LODWORD(v9) = 0;
      }
      InternetSetOptionA(*(HINTERNET *)(dwContext + 56), 0x1Cu, v3, v9 + 1);
      if ( v2 )
      {
        do
          ++v8;
        while ( *((_BYTE *)v2 + v8) );
      }
      else
      {
        LODWORD(v8) = 0;
      }
      InternetSetOptionA(*(HINTERNET *)(dwContext + 56), 0x1Du, v2, v8 + 1);
      if ( *(_DWORD *)(dwContext + 256) )
      {
        v6 = -2146644969;
      }
      else
      {
        v10 = (const CHAR *)CHTTPMailTransport::CommandToVerb(dwContext, *(unsigned int *)(dwContext + 584));
        v11 = HttpOpenRequestA(
                *(HINTERNET *)(dwContext + 56),
                v10,
                lpszObjectName,
                0,
                0,
                *(LPCSTR **)(dwContext + 240),
                0xA0400000,
                0);
        *(_QWORD *)(dwContext + 248) = v11;
        if ( !v11 )
        {
          GetLastError();
          v6 = -2147467259;
        }
      }
    }
  }
  if ( lpszServerName )
    ((void (__fastcall *)(LPMALLOC, LPCSTR))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpszServerName);
  if ( lpszObjectName )
    ((void (__fastcall *)(LPMALLOC, LPCSTR))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpszObjectName);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a2e58  mov     r11, rsp
0x1800a2e5b  push    rbx
0x1800a2e5c  push    rbp
0x1800a2e5d  push    rsi
0x1800a2e5e  push    rdi
0x1800a2e5f  push    r14
0x1800a2e61  sub     rsp, 40h
0x1800a2e65  xor     eax, eax
0x1800a2e67  mov     qword ptr [r11+10h], 0
0x1800a2e6f  lea     rdx, [rcx+4B8h]
0x1800a2e76  mov     [rsp+68h+arg_0], ax
0x1800a2e7b  lea     rax, [rcx+3B8h]
0x1800a2e82  mov     qword ptr [r11+18h], 0
0x1800a2e8a  test    rax, rax
0x1800a2e8d  lea     r14, dword_1800D8644
0x1800a2e94  mov     rbp, r14
0x1800a2e97  lea     r9, [r11+8]; unsigned __int16 *
0x1800a2e9b  cmovnz  rbp, rax
0x1800a2e9f  lea     r8, [r11+18h]; char **
0x1800a2ea3  test    rdx, rdx
0x1800a2ea6  mov     rbx, rcx
0x1800a2ea9  mov     rcx, [rcx+0C0h]; lpszUrl
0x1800a2eb0  cmovnz  r14, rdx
0x1800a2eb4  lea     rdx, [r11+10h]; char **
0x1800a2eb8  call    ?HrCrackUrl@@YAJPEBDPEAPEAD1PEAG@Z; HrCrackUrl(char const *,char * *,char * *,ushort *)
0x1800a2ebd  mov     esi, eax
0x1800a2ebf  test    eax, eax
0x1800a2ec1  js      loc_1800A2FB0
0x1800a2ec7  movzx   r8d, [rsp+68h+arg_0]; unsigned __int16
0x1800a2ecd  mov     rcx, rbx; dwContext
0x1800a2ed0  mov     rdx, [rsp+68h+lpszServerName]; lpszServerName
0x1800a2ed5  call    ?HrConnectToHost@CHTTPMailTransport@@QEAAJPEADG00@Z; CHTTPMailTransport::HrConnectToHost(char *,ushort,char *,char *)
0x1800a2eda  mov     esi, eax
0x1800a2edc  test    eax, eax
0x1800a2ede  js      loc_1800A2FB0
0x1800a2ee4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a2ee8  test    rbp, rbp
0x1800a2eeb  jz      short loc_1800A2EFC
0x1800a2eed  mov     r9, rdi
0x1800a2ef0  inc     r9
0x1800a2ef3  cmp     byte ptr [r9+rbp], 0
0x1800a2ef8  jnz     short loc_1800A2EF0
0x1800a2efa  jmp     short loc_1800A2EFF
0x1800a2efc  xor     r9d, r9d
0x1800a2eff  mov     rcx, [rbx+38h]; hInternet
0x1800a2f03  inc     r9d; dwBufferLength
0x1800a2f06  mov     r8, rbp; lpBuffer
0x1800a2f09  mov     edx, 1Ch; dwOption
0x1800a2f0e  call    cs:__imp_InternetSetOptionA
0x1800a2f14  test    r14, r14
0x1800a2f17  jz      short loc_1800A2F25
0x1800a2f19  inc     rdi
0x1800a2f1c  cmp     byte ptr [r14+rdi], 0
0x1800a2f21  jnz     short loc_1800A2F19
0x1800a2f23  jmp     short loc_1800A2F27
0x1800a2f25  xor     edi, edi
0x1800a2f27  mov     rcx, [rbx+38h]; hInternet
0x1800a2f2b  lea     r9d, [rdi+1]; dwBufferLength
0x1800a2f2f  mov     r8, r14; lpBuffer
0x1800a2f32  mov     edx, 1Dh; dwOption
0x1800a2f37  call    cs:__imp_InternetSetOptionA
0x1800a2f3d  cmp     dword ptr [rbx+100h], 0
0x1800a2f44  jz      short loc_1800A2F4D
0x1800a2f46  mov     esi, 800CCC17h
0x1800a2f4b  jmp     short loc_1800A2FB0
0x1800a2f4d  mov     edx, [rbx+248h]
0x1800a2f53  mov     rcx, rbx
0x1800a2f56  call    ?CommandToVerb@CHTTPMailTransport@@QEAAPEADW4tagHTTPMAILCOMMAND@@@Z; CHTTPMailTransport::CommandToVerb(tagHTTPMAILCOMMAND)
0x1800a2f5b  mov     rcx, [rbx+0F0h]
0x1800a2f62  xor     r9d, r9d; lpszVersion
0x1800a2f65  mov     r8, [rsp+68h+lpszObjectName]; lpszObjectName
0x1800a2f6d  mov     rdx, rax; lpszVerb
0x1800a2f70  mov     [rsp+68h+dwContext], 0; dwContext
0x1800a2f79  mov     [rsp+68h+dwFlags], 0A0400000h; dwFlags
0x1800a2f81  mov     [rsp+68h+lplpszAcceptTypes], rcx; lplpszAcceptTypes
0x1800a2f86  mov     rcx, [rbx+38h]; hConnect
0x1800a2f8a  mov     [rsp+68h+lpszReferrer], 0; lpszReferrer
0x1800a2f93  call    cs:__imp_HttpOpenRequestA
0x1800a2f99  mov     [rbx+0F8h], rax
0x1800a2fa0  test    rax, rax
0x1800a2fa3  jnz     short loc_1800A2FB0
0x1800a2fa5  call    cs:__imp_GetLastError
0x1800a2fab  mov     esi, 80004005h
0x1800a2fb0  cmp     [rsp+68h+lpszServerName], 0
0x1800a2fb6  jz      short loc_1800A2FD0
0x1800a2fb8  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800a2fbf  mov     rdx, [rsp+68h+lpszServerName]
0x1800a2fc4  mov     rax, [rcx]
0x1800a2fc7  mov     rax, [rax+28h]
0x1800a2fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2fd0  cmp     [rsp+68h+lpszObjectName], 0
0x1800a2fd9  jz      short loc_1800A2FF6
0x1800a2fdb  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800a2fe2  mov     rdx, [rsp+68h+lpszObjectName]
0x1800a2fea  mov     rax, [rcx]
0x1800a2fed  mov     rax, [rax+28h]
0x1800a2ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ff6  mov     eax, esi
0x1800a2ff8  add     rsp, 40h
0x1800a2ffc  pop     r14
0x1800a2ffe  pop     rdi
0x1800a2fff  pop     rsi
0x1800a3000  pop     rbp
0x1800a3001  pop     rbx
0x1800a3002  retn
```
