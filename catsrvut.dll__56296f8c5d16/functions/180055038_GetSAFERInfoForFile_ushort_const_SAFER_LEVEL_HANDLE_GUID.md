# GetSAFERInfoForFile(ushort const *,SAFER_LEVEL_HANDLE__ * *,_GUID *)

- ea: `0x180055038`
- end: `0x18005524f`
- name: `?GetSAFERInfoForFile@@YAJPEBGPEAPEAUSAFER_LEVEL_HANDLE__@@PEAU_GUID@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct SAFER_LEVEL_HANDLE__ **, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054f78`

## callees

- `0x180055038`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800551dd`
- `ADVAPI32!SaferIdentifyLevel` at `0x1800550d5`
- `ADVAPI32!SaferIdentifyLevel` at `0x1800550d5`
- `ADVAPI32!SaferCloseLevel` at `0x18005522a`
- `ADVAPI32!SaferCloseLevel` at `0x18005522a`
- `ADVAPI32!SaferGetLevelInformation` at `0x18005511c`
- `ADVAPI32!SaferGetLevelInformation` at `0x1800551d3`
- `ADVAPI32!SaferGetLevelInformation` at `0x18005511c`
- `ADVAPI32!SaferGetLevelInformation` at `0x1800551d3`

## pseudocode

```c
__int64 __fastcall GetSAFERInfoForFile(const unsigned __int16 *a1, struct SAFER_LEVEL_HANDLE__ **a2, struct _GUID *a3)
{
  signed int v5; // ebx
  _DWORD *v6; // rdi
  signed int LastError; // eax
  _OWORD *v8; // rax
  DWORD v9; // r9d
  _OWORD *v10; // rcx
  __int64 v11; // r8
  __int128 v12; // xmm1
  signed int v13; // eax
  DWORD dwOutBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+38h] [rbp-C8h] BYREF
  SAFER_CODE_PROPERTIES_V2 pCodeProperties; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD QueryBuffer[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v19[552]; // [rsp+F8h] [rbp-8h] BYREF

  pCodeProperties.ImagePath = a1;
  pCodeProperties.cbSize = 176;
  pCodeProperties.dwCheckFlags = 1;
  memset_0(&pCodeProperties.hImageFileHandle, 0, 0xA0u);
  v5 = 0;
  dwOutBufferSize = 0;
  pLevelHandle = 0;
  QueryBuffer[0] = 1;
  QueryBuffer[1] = 560;
  memset_0(v19, 0, sizeof(v19));
  *a2 = 0;
  *a3 = GUID_NULL;
  if ( SaferIdentifyLevel(1u, &pCodeProperties, &pLevelHandle, 0) )
    goto LABEL_5;
  v6 = 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_5:
    SaferGetLevelInformation(pLevelHandle, SaferObjectSingleIdentification, QueryBuffer, 0x230u, &dwOutBufferSize);
    dwOutBufferSize += 560;
    v8 = CoTaskMemAlloc(dwOutBufferSize);
    v6 = v8;
    if ( v8 )
    {
      v9 = dwOutBufferSize;
      v10 = QueryBuffer;
      v11 = 4;
      do
      {
        *v8 = *v10;
        v8[1] = v10[1];
        v8[2] = v10[2];
        v8[3] = v10[3];
        v8[4] = v10[4];
        v8[5] = v10[5];
        v8[6] = v10[6];
        v12 = v10[7];
        v10 += 8;
        v8[7] = v12;
        v8 += 8;
        --v11;
      }
      while ( v11 );
      *v8 = *v10;
      v8[1] = v10[1];
      v8[2] = v10[2];
      if ( SaferGetLevelInformation(pLevelHandle, SaferObjectSingleIdentification, v6, v9, &dwOutBufferSize) )
        goto LABEL_22;
      v13 = GetLastError();
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_22:
        if ( *v6 )
        {
          *a2 = pLevelHandle;
          *a3 = *(struct _GUID *)(v6 + 2);
        }
        else
        {
          v5 = -2147023728;
        }
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  CoTaskMemFree(v6);
  if ( v5 < 0 && pLevelHandle )
    SaferCloseLevel(pLevelHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180055038  push    rbp
0x18005503a  push    rbx
0x18005503b  push    rsi
0x18005503c  push    rdi
0x18005503d  push    r14
0x18005503f  lea     rbp, [rsp-230h]
0x180055047  sub     rsp, 330h
0x18005504e  mov     rax, cs:__security_cookie
0x180055055  xor     rax, rsp
0x180055058  mov     [rbp+250h+var_30], rax
0x18005505f  mov     r14, r8
0x180055062  mov     [rsp+350h+pCodeProperties.ImagePath], rcx
0x180055067  mov     rsi, rdx
0x18005506a  mov     [rsp+350h+pCodeProperties.cbSize], 0B0h
0x180055072  mov     edi, 1
0x180055077  lea     rcx, [rsp+350h+pCodeProperties.hImageFileHandle]; void *
0x18005507c  xor     edx, edx; Val
0x18005507e  mov     [rsp+350h+pCodeProperties.dwCheckFlags], edi
0x180055082  mov     r8d, 0A0h; Size
0x180055088  call    memset_0
0x18005508d  xor     ebx, ebx
0x18005508f  mov     [rsp+350h+dwOutBufferSize], 0
0x180055097  xor     edx, edx; Val
0x180055099  mov     [rsp+350h+pLevelHandle], rbx
0x18005509e  mov     r8d, 228h; Size
0x1800550a4  mov     [rbp+250h+QueryBuffer], edi
0x1800550a7  lea     rcx, [rbp+250h+var_258]; void *
0x1800550ab  mov     [rbp+250h+var_25C], 230h
0x1800550b2  call    memset_0
0x1800550b7  mov     [rsi], rbx
0x1800550ba  lea     r8, [rsp+350h+pLevelHandle]; pLevelHandle
0x1800550bf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800550c6  xor     r9d, r9d; lpReserved
0x1800550c9  lea     rdx, [rsp+350h+pCodeProperties]; pCodeProperties
0x1800550ce  mov     ecx, edi; dwNumProperties
0x1800550d0  movdqu  xmmword ptr [r14], xmm0
0x1800550d5  call    cs:__imp_SaferIdentifyLevel
0x1800550db  test    eax, eax
0x1800550dd  jnz     short loc_1800550FE
0x1800550df  xor     edi, edi
0x1800550e1  call    cs:__imp_GetLastError
0x1800550e7  mov     ebx, eax
0x1800550e9  test    eax, eax
0x1800550eb  jle     short loc_1800550F6
0x1800550ed  movzx   ebx, ax
0x1800550f0  or      ebx, 80070000h
0x1800550f6  test    ebx, ebx
0x1800550f8  js      loc_180055213
0x1800550fe  mov     rcx, [rsp+350h+pLevelHandle]; LevelHandle
0x180055103  lea     rax, [rsp+350h+dwOutBufferSize]
0x180055108  mov     r9d, 230h; dwInBufferSize
0x18005510e  mov     [rsp+350h+lpdwOutBufferSize], rax; lpdwOutBufferSize
0x180055113  lea     r8, [rbp+250h+QueryBuffer]; lpQueryBuffer
0x180055117  mov     edx, 0Fh; dwInfoType
0x18005511c  call    cs:__imp_SaferGetLevelInformation
0x180055122  mov     eax, [rsp+350h+dwOutBufferSize]
0x180055126  add     eax, 230h
0x18005512b  mov     ecx, eax; cb
0x18005512d  mov     [rsp+350h+dwOutBufferSize], eax
0x180055131  call    cs:__imp_CoTaskMemAlloc
0x180055137  mov     rdi, rax
0x18005513a  test    rax, rax
0x18005513d  jnz     short loc_180055149
0x18005513f  mov     ebx, 8007000Eh
0x180055144  jmp     loc_180055213
0x180055149  mov     r9d, [rsp+350h+dwOutBufferSize]; dwInBufferSize
0x18005514e  lea     rcx, [rbp+250h+QueryBuffer]
0x180055152  mov     r8d, 4
0x180055158  lea     r10d, [r8+7Ch]
0x18005515c  movups  xmm0, xmmword ptr [rcx]
0x18005515f  movups  xmmword ptr [rax], xmm0
0x180055162  movups  xmm1, xmmword ptr [rcx+10h]
0x180055166  movups  xmmword ptr [rax+10h], xmm1
0x18005516a  movups  xmm0, xmmword ptr [rcx+20h]
0x18005516e  movups  xmmword ptr [rax+20h], xmm0
0x180055172  movups  xmm1, xmmword ptr [rcx+30h]
0x180055176  movups  xmmword ptr [rax+30h], xmm1
0x18005517a  movups  xmm0, xmmword ptr [rcx+40h]
0x18005517e  movups  xmmword ptr [rax+40h], xmm0
0x180055182  movups  xmm1, xmmword ptr [rcx+50h]
0x180055186  movups  xmmword ptr [rax+50h], xmm1
0x18005518a  movups  xmm0, xmmword ptr [rcx+60h]
0x18005518e  movups  xmmword ptr [rax+60h], xmm0
0x180055192  movups  xmm1, xmmword ptr [rcx+70h]
0x180055196  add     rcx, r10
0x180055199  movups  xmmword ptr [rax+70h], xmm1
0x18005519d  add     rax, r10
0x1800551a0  sub     r8, 1
0x1800551a4  jnz     short loc_18005515C
0x1800551a6  movups  xmm0, xmmword ptr [rcx]
0x1800551a9  mov     r8, rdi; lpQueryBuffer
0x1800551ac  mov     edx, 0Fh; dwInfoType
0x1800551b1  movups  xmmword ptr [rax], xmm0
0x1800551b4  movups  xmm1, xmmword ptr [rcx+10h]
0x1800551b8  movups  xmmword ptr [rax+10h], xmm1
0x1800551bc  movups  xmm0, xmmword ptr [rcx+20h]
0x1800551c0  movups  xmmword ptr [rax+20h], xmm0
0x1800551c4  mov     rcx, [rsp+350h+pLevelHandle]; LevelHandle
0x1800551c9  lea     rax, [rsp+350h+dwOutBufferSize]
0x1800551ce  mov     [rsp+350h+lpdwOutBufferSize], rax; lpdwOutBufferSize
0x1800551d3  call    cs:__imp_SaferGetLevelInformation
0x1800551d9  test    eax, eax
0x1800551db  jnz     short loc_1800551F6
0x1800551dd  call    cs:__imp_GetLastError
0x1800551e3  mov     ebx, eax
0x1800551e5  test    eax, eax
0x1800551e7  jle     short loc_1800551F2
0x1800551e9  movzx   ebx, ax
0x1800551ec  or      ebx, 80070000h
0x1800551f2  test    ebx, ebx
0x1800551f4  js      short loc_180055213
0x1800551f6  cmp     dword ptr [rdi], 0
0x1800551f9  jnz     short loc_180055202
0x1800551fb  mov     ebx, 80070490h
0x180055200  jmp     short loc_180055213
0x180055202  mov     rax, [rsp+350h+pLevelHandle]
0x180055207  mov     [rsi], rax
0x18005520a  movups  xmm0, xmmword ptr [rdi+8]
0x18005520e  movdqu  xmmword ptr [r14], xmm0
0x180055213  mov     rcx, rdi; pv
0x180055216  call    cs:__imp_CoTaskMemFree
0x18005521c  test    ebx, ebx
0x18005521e  jns     short loc_180055230
0x180055220  mov     rcx, [rsp+350h+pLevelHandle]; hLevelHandle
0x180055225  test    rcx, rcx
0x180055228  jz      short loc_180055230
0x18005522a  call    cs:__imp_SaferCloseLevel
0x180055230  mov     eax, ebx
0x180055232  mov     rcx, [rbp+250h+var_30]
0x180055239  xor     rcx, rsp; StackCookie
0x18005523c  call    __security_check_cookie
0x180055241  add     rsp, 330h
0x180055248  pop     r14
0x18005524a  pop     rdi
0x18005524b  pop     rsi
0x18005524c  pop     rbx
0x18005524d  pop     rbp
0x18005524e  retn
```
