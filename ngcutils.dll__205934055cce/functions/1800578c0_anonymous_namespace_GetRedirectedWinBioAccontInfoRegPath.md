# _anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath

- ea: `0x1800578c0`
- end: `0x18005798c`
- name: `_anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057994`
- `0x180057bec`

## callees

- `0x18000530d`
- `0x18000a5b4`
- `0x180014458`
- `0x180015ca4`
- `0x1800578c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005791a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005797b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005791a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005797b`

## string_xrefs

- `0x180057900`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::GetRedirectedWinBioAccontInfoRegPath(char **a1)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v3; // edi
  HLOCAL v5; // rdi
  unsigned __int64 v6; // rdx
  char *v7; // rsi
  __int64 v8; // rbx
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  hMem = 0;
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"WinBio",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
                                        L"AccountInfo\\",
                                        &hMem);
  v3 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v5 = hMem;
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)hMem + v6) );
    if ( v6 > (unsigned __int64)a1[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1);
    }
    else
    {
      if ( (unsigned __int64)a1[3] <= 7 )
        v7 = (char *)a1;
      else
        v7 = *a1;
      a1[2] = (char *)v6;
      v8 = 2 * v6;
      memmove_0(v7, v5, 2 * v6);
      *(_WORD *)&v7[v8] = 0;
    }
    if ( v5 )
      LocalFree(v5);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      v9);
    if ( hMem )
      LocalFree(hMem);
    return v3;
  }
}

```

## disassembly

```asm
0x1800578c0  push    rbx
0x1800578c2  push    rbp
0x1800578c3  push    rsi
0x1800578c4  push    rdi
0x1800578c5  sub     rsp, 28h
0x1800578c9  mov     rbx, rcx
0x1800578cc  xor     ebp, ebp
0x1800578ce  mov     [rsp+48h+hMem], rbp
0x1800578d3  lea     r9, [rsp+48h+hMem]; unsigned __int16 *
0x1800578d8  lea     r8, aAccountinfo; "AccountInfo\\"
0x1800578df  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800578e6  lea     rcx, aWinbio; "WinBio"
0x1800578ed  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800578f2  mov     edi, eax
0x1800578f4  test    eax, eax
0x1800578f6  jns     short loc_180057924
0x1800578f8  mov     rcx, [rsp+48h]; this
0x1800578fd  mov     r9d, eax; char *
0x180057900  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180057907  lea     edx, [rbp+20h]; void *
0x18005790a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005790f  nop
0x180057910  mov     rcx, [rsp+48h+hMem]; hMem
0x180057915  test    rcx, rcx
0x180057918  jz      short loc_180057920
0x18005791a  call    cs:__imp_LocalFree
0x180057920  mov     eax, edi
0x180057922  jmp     short loc_180057983
0x180057924  mov     rdi, [rsp+48h+hMem]
0x180057929  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005792d  inc     rdx
0x180057930  cmp     [rdi+rdx*2], bp
0x180057934  jnz     short loc_18005792D
0x180057936  cmp     rdx, [rbx+18h]
0x18005793a  ja      short loc_180057967
0x18005793c  cmp     qword ptr [rbx+18h], 7
0x180057941  jbe     short loc_180057948
0x180057943  mov     rsi, [rbx]
0x180057946  jmp     short loc_18005794B
0x180057948  mov     rsi, rbx
0x18005794b  mov     [rbx+10h], rdx
0x18005794f  lea     rbx, [rdx+rdx]
0x180057953  mov     r8, rbx; Size
0x180057956  mov     rdx, rdi; Src
0x180057959  mov     rcx, rsi; void *
0x18005795c  call    memmove_0
0x180057961  mov     [rbx+rsi], bp
0x180057965  jmp     short loc_180057973
0x180057967  mov     r9, rdi
0x18005796a  mov     rcx, rbx
0x18005796d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180057972  nop
0x180057973  test    rdi, rdi
0x180057976  jz      short loc_180057981
0x180057978  mov     rcx, rdi; hMem
0x18005797b  call    cs:__imp_LocalFree
0x180057981  xor     eax, eax
0x180057983  add     rsp, 28h
0x180057987  pop     rdi
0x180057988  pop     rsi
0x180057989  pop     rbp
0x18005798a  pop     rbx
0x18005798b  retn
```
