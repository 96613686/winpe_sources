# CCertGetConfig::GetConfig(long,ushort * *)

- ea: `0x18000daa0`
- end: `0x18000dbaa`
- name: `?GetConfig@CCertGetConfig@@UEAAJJPEAPEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CCertGetConfig *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x18000a68c`
- `0x18000b940`
- `0x18000b9cc`
- `0x18000daa0`
- `0x18001d000`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000daf9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000daf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db5d`
- `certca!__imp_?myGetErrorMessageText@@YAPEAGJK@Z` at `0x18000dac7`
- `certca!__imp_?myGetErrorMessageText@@YAPEAGJK@Z` at `0x18000dac7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000db11`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000db41`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000db11`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000db41`

## string_xrefs

- `0x18000db25`: `CertificateAuthority.GetConfig`
- `0x18000db17`: `CCertGetConfig::GetConfig`
- `0x18000db70`: `CCertGetConfig::GetConfig`

## pseudocode

```c
__int64 __fastcall CCertGetConfig::GetConfig(CCertGetConfig *this, int a2, unsigned __int16 **a3)
{
  int Config; // eax
  unsigned int v4; // esi
  unsigned __int16 *v5; // rbx
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 *ErrorMessageText; // rdi
  unsigned int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r8
  int v15; // eax
  IErrorInfo *v17; // [rsp+28h] [rbp-40h]

  Config = CCertConfigPrivate::GetConfig((CCertGetConfig *)((char *)this + 72), a2, a3);
  v4 = Config;
  if ( Config >= 0 )
    return v4;
  v5 = 0;
  ErrorMessageText = myGetErrorMessageText(Config, 1u);
  if ( ErrorMessageText )
  {
    v10 = -1;
    do
      ++v10;
    while ( ErrorMessageText[v10] );
    v11 = v10 + 2;
    if ( !v11 )
      goto LABEL_10;
    v12 = v11 + 26;
    v13 = (unsigned __int16 *)LocalAlloc(0, 2 * (v11 + 26));
    v5 = v13;
    if ( v13 )
    {
      StringCchCopyW(v13, v12, L"CCertGetConfig::GetConfig");
      StringCchCatW(v5, v12, L": ");
      StringCchCatW(v5, v12, ErrorMessageText);
      v14 = v5;
      goto LABEL_11;
    }
    v9 = 53412266;
  }
  else
  {
    v9 = 52232618;
  }
  CSPrintErrorLineFile(v9, -2147024882);
LABEL_10:
  v14 = L"CCertGetConfig::GetConfig";
LABEL_11:
  v15 = DispatchSetErrorInfoSub(v7, v6, v14, L"CertificateAuthority.GetConfig", &IID_ICertGetConfig, v17);
  if ( v15 )
    CSPrintErrorLineFile(0x34901AAu, v15);
  if ( v5 )
    LocalFree(v5);
  if ( ErrorMessageText )
    LocalFree(ErrorMessageText);
  return v4;
}

```

## disassembly

```asm
0x18000daa0  push    rbx
0x18000daa2  push    rbp
0x18000daa3  push    rsi
0x18000daa4  push    rdi
0x18000daa5  push    r14
0x18000daa7  sub     rsp, 40h
0x18000daab  add     rcx, 48h ; 'H'; this
0x18000daaf  call    ?GetConfig@CCertConfigPrivate@@QEAAJJPEAPEAG@Z; CCertConfigPrivate::GetConfig(long,ushort * *)
0x18000dab4  xor     ebp, ebp
0x18000dab6  mov     esi, eax
0x18000dab8  test    eax, eax
0x18000daba  jns     loc_18000DB63
0x18000dac0  lea     edx, [rbp+1]
0x18000dac3  mov     ecx, eax
0x18000dac5  mov     ebx, ebp
0x18000dac7  call    cs:__imp_?myGetErrorMessageText@@YAPEAGJK@Z; myGetErrorMessageText(long,ulong)
0x18000dacd  mov     rdi, rax
0x18000dad0  test    rax, rax
0x18000dad3  jnz     short loc_18000DADC
0x18000dad5  mov     ecx, 31D01AAh
0x18000dada  jmp     short loc_18000DB0C
0x18000dadc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dae0  inc     rax
0x18000dae3  cmp     [rdi+rax*2], bp
0x18000dae7  jnz     short loc_18000DAE0
0x18000dae9  add     rax, 2
0x18000daed  jz      short loc_18000DB17
0x18000daef  lea     r14, [rax+1Ah]
0x18000daf3  xor     ecx, ecx; uFlags
0x18000daf5  lea     rdx, [r14+r14]; uBytes
0x18000daf9  call    cs:__imp_LocalAlloc
0x18000daff  mov     rbx, rax
0x18000db02  test    rax, rax
0x18000db05  jnz     short loc_18000DB70
0x18000db07  mov     ecx, 32F01AAh
0x18000db0c  mov     edx, 8007000Eh
0x18000db11  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000db17  lea     r8, aCcertgetconfig; "CCertGetConfig::GetConfig"
0x18000db1e  lea     rax, IID_ICertGetConfig
0x18000db25  lea     r9, aCertificateaut_1; "CertificateAuthority.GetConfig"
0x18000db2c  mov     [rsp+68h+var_48], rax; struct _GUID *
0x18000db31  call    ?DispatchSetErrorInfoSub@@YAJJPEBG00PEBU_GUID@@0K@Z; DispatchSetErrorInfoSub(long,ushort const *,ushort const *,ushort const *,_GUID const *,ushort const *,ulong)
0x18000db36  test    eax, eax
0x18000db38  jz      short loc_18000DB47
0x18000db3a  mov     edx, eax
0x18000db3c  mov     ecx, 34901AAh
0x18000db41  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000db47  test    rbx, rbx
0x18000db4a  jz      short loc_18000DB55
0x18000db4c  mov     rcx, rbx; hMem
0x18000db4f  call    cs:__imp_LocalFree
0x18000db55  test    rdi, rdi
0x18000db58  jz      short loc_18000DB63
0x18000db5a  mov     rcx, rdi; hMem
0x18000db5d  call    cs:__imp_LocalFree
0x18000db63  mov     eax, esi
0x18000db65  add     rsp, 40h
0x18000db69  pop     r14
0x18000db6b  pop     rdi
0x18000db6c  pop     rsi
0x18000db6d  pop     rbp
0x18000db6e  pop     rbx
0x18000db6f  retn
0x18000db70  lea     r8, aCcertgetconfig; "CCertGetConfig::GetConfig"
0x18000db77  mov     rdx, r14; unsigned __int64
0x18000db7a  mov     rcx, rbx; unsigned __int16 *
0x18000db7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000db82  lea     r8, asc_180053790; ": "
0x18000db89  mov     rdx, r14; unsigned __int64
0x18000db8c  mov     rcx, rbx; unsigned __int16 *
0x18000db8f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000db94  mov     r8, rdi; unsigned __int16 *
0x18000db97  mov     rdx, r14; unsigned __int64
0x18000db9a  mov     rcx, rbx; unsigned __int16 *
0x18000db9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dba2  mov     r8, rbx
0x18000dba5  jmp     loc_18000DB1E
```
