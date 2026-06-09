# CJob::GetAccountInformation(ushort * *)

- ea: `0x18000b740`
- end: `0x18000b902`
- name: `?GetAccountInformation@CJob@@UEAAJPEAPEAG@Z`
- size: `450`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x180008450`
- `0x18000b660`
- `0x18000b740`
- `0x18000b920`
- `0x18000ca2c`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000b82d`
- `msvcrt!wcsrchr` at `0x18000b82d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b8a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b8a9`

## pseudocode

```c
__int64 __fastcall CJob::GetAccountInformation(CJob *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rsi
  signed int ServerNameFromPath; // edi
  const unsigned __int16 **v6; // rax
  int v7; // edx
  unsigned int v8; // r8d
  unsigned __int16 *v9; // r14
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int64 v14; // r14
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r10
  unsigned __int16 *v18; // [rsp+20h] [rbp-678h] BYREF
  signed int v19; // [rsp+28h] [rbp-670h]
  unsigned __int16 **v20; // [rsp+30h] [rbp-668h]
  _BYTE v21[528]; // [rsp+40h] [rbp-658h] BYREF
  unsigned __int16 v22[264]; // [rsp+250h] [rbp-448h] BYREF
  unsigned __int16 v23[264]; // [rsp+460h] [rbp-238h] BYREF

  v20 = a2;
  v4 = (const unsigned __int16 *)*((_QWORD *)this + 19);
  if ( !v4 )
    return (unsigned int)-2147418113;
  memset_0(v21, 0, 0x202u);
  v6 = (const unsigned __int16 **)*((_QWORD *)this + 25);
  if ( v6 )
  {
    v12 = *v6;
    if ( !*v6 )
      return (unsigned int)-2147418113;
    ServerNameFromPath = 0;
    goto LABEL_15;
  }
  memset_0(v22, 0, 0x20Au);
  memset_0(v23, 0, 0x20Au);
  v18 = 0;
  ServerNameFromPath = GetServerNameFromPath(v4, v7, v22, (const unsigned __int16 **)&v18);
  if ( ServerNameFromPath >= 0 )
  {
    v9 = v18;
    if ( v18 )
    {
      ServerNameFromPath = ResolveTarget((const unsigned __int16 **)&v18, v23, v8);
      v9 = v18;
    }
    if ( ServerNameFromPath >= 0 )
    {
      v10 = wcsrchr(v4, 0x5Cu);
      if ( v10 )
        v11 = v10 + 1;
      else
        v11 = v4;
      ServerNameFromPath = SAGetAccountInformation(v9, v11, 256, v21);
      v19 = ServerNameFromPath;
      v12 = 0;
      if ( ServerNameFromPath >= 0 )
        v12 = (const unsigned __int16 *)v21;
LABEL_15:
      if ( v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        v14 = v13 + 1;
        v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v13 + 1));
        if ( v15 )
        {
          *v15 = 0;
          StringCchCopyW(v15, v14, v12);
          *a2 = v16;
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        *a2 = 0;
      }
    }
  }
  return (unsigned int)ServerNameFromPath;
}

```

## disassembly

```asm
0x18000b740  mov     [rsp+arg_10], rbx
0x18000b745  mov     [rsp+arg_18], rsi
0x18000b74a  push    rdi
0x18000b74b  push    r14
0x18000b74d  push    r15
0x18000b74f  sub     rsp, 680h
0x18000b756  mov     rax, cs:__security_cookie
0x18000b75d  xor     rax, rsp
0x18000b760  mov     [rsp+698h+var_28], rax
0x18000b768  mov     r15, rdx
0x18000b76b  mov     rdi, rcx
0x18000b76e  mov     [rsp+698h+var_668], rdx
0x18000b773  mov     rsi, [rcx+98h]
0x18000b77a  xor     ebx, ebx
0x18000b77c  test    rsi, rsi
0x18000b77f  jnz     short loc_18000B78B
0x18000b781  mov     edi, 8000FFFFh
0x18000b786  jmp     loc_18000B8D7
0x18000b78b  xor     edx, edx; Val
0x18000b78d  mov     r8d, 202h; Size
0x18000b793  lea     rcx, [rsp+698h+var_658]; void *
0x18000b798  call    memset_0
0x18000b79d  mov     rax, [rdi+0C8h]
0x18000b7a4  test    rax, rax
0x18000b7a7  jnz     loc_18000B881
0x18000b7ad  mov     edi, 20Ah
0x18000b7b2  mov     r8d, edi; Size
0x18000b7b5  xor     edx, edx; Val
0x18000b7b7  lea     rcx, [rsp+698h+var_448]; void *
0x18000b7bf  call    memset_0
0x18000b7c4  mov     r8d, edi; Size
0x18000b7c7  xor     edx, edx; Val
0x18000b7c9  lea     rcx, [rsp+698h+var_238]; void *
0x18000b7d1  call    memset_0
0x18000b7d6  mov     [rsp+698h+var_678], rbx
0x18000b7db  lea     r9, [rsp+698h+var_678]; unsigned __int16 **
0x18000b7e0  lea     r8, [rsp+698h+var_448]; unsigned __int16 *
0x18000b7e8  mov     rcx, rsi; unsigned __int16 *
0x18000b7eb  call    ?GetServerNameFromPath@@YAJPEBGKPEAGPEAPEBG@Z; GetServerNameFromPath(ushort const *,ulong,ushort *,ushort const * *)
0x18000b7f0  mov     edi, eax
0x18000b7f2  test    eax, eax
0x18000b7f4  js      loc_18000B8D7
0x18000b7fa  mov     r14, [rsp+698h+var_678]
0x18000b7ff  test    r14, r14
0x18000b802  jz      short loc_18000B81D
0x18000b804  lea     rdx, [rsp+698h+var_238]; unsigned __int16 *
0x18000b80c  lea     rcx, [rsp+698h+var_678]; unsigned __int16 **
0x18000b811  call    ?ResolveTarget@@YAJPEAPEBGPEAGK@Z; ResolveTarget(ushort const * *,ushort *,ulong)
0x18000b816  mov     edi, eax
0x18000b818  mov     r14, [rsp+698h+var_678]
0x18000b81d  test    edi, edi
0x18000b81f  js      loc_18000B8D7
0x18000b825  mov     edx, 5Ch ; '\'; Ch
0x18000b82a  mov     rcx, rsi; Str
0x18000b82d  call    cs:__imp_wcsrchr
0x18000b833  test    rax, rax
0x18000b836  jz      short loc_18000B83E
0x18000b838  add     rax, 2
0x18000b83c  jmp     short loc_18000B841
0x18000b83e  mov     rax, rsi
0x18000b841  lea     r9, [rsp+698h+var_658]
0x18000b846  mov     r8d, 100h
0x18000b84c  mov     rdx, rax
0x18000b84f  mov     rcx, r14
0x18000b852  call    SAGetAccountInformation
0x18000b857  mov     edi, eax
0x18000b859  mov     [rsp+698h+var_670], eax
0x18000b85d  jmp     short loc_18000B873
0x18000b85f  mov     ecx, eax; unsigned int
0x18000b861  call    ?SchedMapRpcError@@YAJK@Z; SchedMapRpcError(ulong)
0x18000b866  mov     edi, eax
0x18000b868  mov     [rsp+698h+var_670], eax
0x18000b86c  xor     ebx, ebx
0x18000b86e  mov     r15, [rsp+698h+var_668]
0x18000b873  mov     rsi, rbx
0x18000b876  test    edi, edi
0x18000b878  js      short loc_18000B88F
0x18000b87a  lea     rsi, [rsp+698h+var_658]
0x18000b87f  jmp     short loc_18000B88F
0x18000b881  mov     rsi, [rax]
0x18000b884  test    rsi, rsi
0x18000b887  jz      loc_18000B781
0x18000b88d  mov     edi, ebx
0x18000b88f  test    rsi, rsi
0x18000b892  jz      short loc_18000B8D4
0x18000b894  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b898  inc     rax
0x18000b89b  cmp     [rsi+rax*2], bx
0x18000b89f  jnz     short loc_18000B898
0x18000b8a1  lea     r14, [rax+1]
0x18000b8a5  lea     rcx, [r14+r14]; cb
0x18000b8a9  call    cs:__imp_CoTaskMemAlloc
0x18000b8af  mov     r10, rax
0x18000b8b2  test    rax, rax
0x18000b8b5  jnz     short loc_18000B8BE
0x18000b8b7  mov     edi, 8007000Eh
0x18000b8bc  jmp     short loc_18000B8D7
0x18000b8be  mov     [rax], bx
0x18000b8c1  mov     r8, rsi; unsigned __int16 *
0x18000b8c4  mov     rdx, r14; unsigned __int64
0x18000b8c7  mov     rcx, r10; unsigned __int16 *
0x18000b8ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b8cf  mov     [r15], r10
0x18000b8d2  jmp     short loc_18000B8D7
0x18000b8d4  mov     [r15], rbx
0x18000b8d7  mov     eax, edi
0x18000b8d9  mov     rcx, [rsp+698h+var_28]
0x18000b8e1  xor     rcx, rsp; StackCookie
0x18000b8e4  call    __security_check_cookie
0x18000b8e9  lea     r11, [rsp+698h+var_18]
0x18000b8f1  mov     rbx, [r11+30h]
0x18000b8f5  mov     rsi, [r11+38h]
0x18000b8f9  mov     rsp, r11
0x18000b8fc  pop     r15
0x18000b8fe  pop     r14
0x18000b900  pop     rdi
0x18000b901  retn
0x18001aea6  push    rbp
0x18001aea8  sub     rsp, 20h
0x18001aeac  mov     rbp, rdx
0x18001aeaf  mov     rcx, [rcx]
0x18001aeb2  mov     ecx, [rcx]; ExceptionCode
0x18001aeb4  call    cs:__imp_I_RpcExceptionFilter
0x18001aeba  nop
0x18001aebb  add     rsp, 20h
0x18001aebf  pop     rbp
0x18001aec0  retn
```
