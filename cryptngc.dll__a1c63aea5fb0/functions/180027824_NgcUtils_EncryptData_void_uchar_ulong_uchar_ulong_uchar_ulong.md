# NgcUtils::EncryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180027824`
- end: `0x180027985`
- name: `?EncryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z`
- size: `353`
- prototype: `__int64 __usercall@<rax>(BCRYPT_KEY_HANDLE hKey@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned int@<r9d>, ULONG, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002cf74`

## callees

- `0x180006538`
- `0x1800065c0`
- `0x180027824`
- `0x180028380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027954`
- `bcrypt!BCryptEncrypt` at `0x180027877`
- `bcrypt!BCryptEncrypt` at `0x180027927`
- `bcrypt!BCryptEncrypt` at `0x180027877`
- `bcrypt!BCryptEncrypt` at `0x180027927`

## string_xrefs

- `0x180027886`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x1800278c5`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180027936`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::EncryptData(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        UCHAR *a4,
        ULONG pcbResult,
        PUCHAR *a6,
        unsigned __int8 **a7)
{
  NTSTATUS v10; // eax
  PUCHAR v12; // rbx
  NTSTATUS v13; // eax
  unsigned int v14; // edi
  unsigned __int8 **v15; // rcx
  int pbIV; // [rsp+20h] [rbp-58h]
  int pbIVa; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  PUCHAR pbOutput; // [rsp+98h] [rbp+20h] BYREF

  pbOutput = a4;
  pcbResult = 0;
  v10 = BCryptEncrypt(hKey, pbInput, cbInput, 0, 0, 0, 0, 0, &pcbResult, 1u);
  if ( v10 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x2B6,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v10,
             pbIV);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&pbOutput, pcbResult);
  v12 = pbOutput;
  if ( pbOutput )
  {
    v13 = BCryptEncrypt(hKey, pbInput, cbInput, 0, 0, 0, pbOutput, pcbResult, &pcbResult, 1u);
    if ( v13 >= 0 )
    {
      v15 = a7;
      *a6 = v12;
      *(_DWORD *)v15 = pcbResult;
      return 0;
    }
    else
    {
      v14 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x2C5,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
              (const char *)(unsigned int)v13,
              pbIVa);
      if ( v12 )
        LocalFree(v12);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pbIV);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180027824  mov     r11, rsp
0x180027827  mov     [r11+20h], r9
0x18002782b  push    rbx
0x18002782c  push    rbp
0x18002782d  push    rsi
0x18002782e  push    rdi
0x18002782f  sub     rsp, 58h
0x180027833  mov     [rsp+78h+dwFlags], 1; dwFlags
0x18002783b  lea     rax, [r11+28h]
0x18002783f  mov     [r11-38h], rax
0x180027843  xor     r9d, r9d; pPaddingInfo
0x180027846  mov     [rsp+78h+cbOutput], 0; cbOutput
0x18002784e  mov     edi, r8d
0x180027851  mov     qword ptr [r11-48h], 0
0x180027859  mov     rsi, rdx
0x18002785c  mov     [rsp+78h+cbIV], 0; cbIV
0x180027864  mov     rbp, rcx
0x180027867  mov     qword ptr [r11-58h], 0
0x18002786f  mov     dword ptr [r11+28h], 0
0x180027877  call    cs:__imp_BCryptEncrypt
0x18002787d  test    eax, eax
0x18002787f  jns     short loc_18002789F
0x180027881  mov     rcx, [rsp+78h]; this
0x180027886  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002788d  mov     r9d, eax; char *
0x180027890  mov     edx, 2B6h; void *
0x180027895  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002789a  jmp     loc_18002797C
0x18002789f  mov     edx, [rsp+78h+arg_20]
0x1800278a6  lea     rcx, [rsp+78h+arg_18]
0x1800278ae  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800278b3  mov     rbx, [rsp+78h+arg_18]
0x1800278bb  test    rbx, rbx
0x1800278be  jnz     short loc_1800278E5
0x1800278c0  mov     rcx, [rsp+78h]; this
0x1800278c5  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800278cc  mov     ebx, 8007000Eh
0x1800278d1  mov     edx, 2B9h; void *
0x1800278d6  mov     r9d, ebx; char *
0x1800278d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800278de  mov     eax, ebx
0x1800278e0  jmp     loc_18002797C
0x1800278e5  mov     eax, [rsp+78h+arg_20]
0x1800278ec  lea     rcx, [rsp+78h+arg_20]
0x1800278f4  mov     [rsp+78h+dwFlags], 1; dwFlags
0x1800278fc  xor     r9d, r9d; pPaddingInfo
0x1800278ff  mov     [rsp+78h+pcbResult], rcx; pcbResult
0x180027904  mov     r8d, edi; cbInput
0x180027907  mov     [rsp+78h+cbOutput], eax; cbOutput
0x18002790b  mov     rdx, rsi; pbInput
0x18002790e  mov     [rsp+78h+pbOutput], rbx; pbOutput
0x180027913  mov     rcx, rbp; hKey
0x180027916  mov     [rsp+78h+cbIV], 0; cbIV
0x18002791e  mov     [rsp+78h+pbIV], 0; int
0x180027927  call    cs:__imp_BCryptEncrypt
0x18002792d  test    eax, eax
0x18002792f  jns     short loc_18002795E
0x180027931  mov     rcx, [rsp+78h]; this
0x180027936  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002793d  mov     r9d, eax; char *
0x180027940  mov     edx, 2C5h; void *
0x180027945  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002794a  mov     edi, eax
0x18002794c  test    rbx, rbx
0x18002794f  jz      short loc_18002795A
0x180027951  mov     rcx, rbx; hMem
0x180027954  call    cs:__imp_LocalFree
0x18002795a  mov     eax, edi
0x18002795c  jmp     short loc_18002797C
0x18002795e  mov     rax, [rsp+78h+arg_28]
0x180027966  mov     rcx, [rsp+78h+arg_30]
0x18002796e  mov     [rax], rbx
0x180027971  mov     eax, [rsp+78h+arg_20]
0x180027978  mov     [rcx], eax
0x18002797a  xor     eax, eax
0x18002797c  add     rsp, 58h
0x180027980  pop     rdi
0x180027981  pop     rsi
0x180027982  pop     rbp
0x180027983  pop     rbx
0x180027984  retn
```
