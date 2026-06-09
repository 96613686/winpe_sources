# WriteQoSPoliciesToRegsitry

- ea: `0x180043aa0`
- end: `0x180043c73`
- name: `WriteQoSPoliciesToRegsitry`
- size: `467`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180043498`
- `0x18004a6c0`
- `0x18004c944`

## callees

- `0x180043aa0`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043be1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043be1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043b49`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043b70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043b49`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043b70`

## string_xrefs

- `0x180043c0a`: `WriteQoSPoliciesToRegsitry`

## pseudocode

```c
__int64 __fastcall WriteQoSPoliciesToRegsitry(HKEY hKey, unsigned int *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // edx
  int v6; // esi
  int v7; // r9d
  __int64 v8; // rcx
  unsigned int v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  const WCHAR *v12; // rbp
  __int64 v13; // rsi
  unsigned int v14; // ecx
  const WCHAR *v15; // rax
  int v17; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-824h] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( a2 && hKey )
  {
    v4 = 0;
    v5 = 0;
    v6 = 1;
    v7 = 1;
    if ( !*a2 )
      goto LABEL_13;
    v8 = 0;
    do
    {
      v9 = a2[3 * v8 + 2];
      if ( v9 )
      {
        if ( v9 == 1 && a2[3 * v8 + 1] )
          v6 = 0;
      }
      else if ( a2[3 * v8 + 1] )
      {
        v7 = 0;
      }
      ++v5;
      ++v8;
    }
    while ( v5 < *a2 );
    if ( v7 )
    {
LABEL_13:
      v10 = RegDeleteValueW(hKey, L"TxBandwidthKbps");
      v4 = v10;
      if ( v10 == 2 )
      {
        v4 = 0;
      }
      else if ( v10 )
      {
        goto LABEL_32;
      }
    }
    if ( v6 )
    {
      v11 = RegDeleteValueW(hKey, L"RxBandwidthKbps");
      v4 = v11;
      if ( v11 == 2 )
      {
        v4 = 0;
      }
      else if ( v11 )
      {
        goto LABEL_32;
      }
    }
    v12 = 0;
    v13 = 0;
    if ( *a2 )
    {
      while ( 1 )
      {
        v14 = a2[3 * v13 + 2];
        if ( v14 )
        {
          v15 = L"RxBandwidthKbps";
          if ( v14 != 1 )
            v15 = v12;
          v12 = v15;
        }
        else
        {
          v12 = L"TxBandwidthKbps";
        }
        if ( a2[3 * v13 + 1] )
        {
          v4 = RegSetValueExW(hKey, v12, 0, 4u, (const BYTE *)&a2[3 * v13 + 1], 4u);
          if ( v4 )
            break;
        }
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= *a2 )
          goto LABEL_29;
      }
    }
    else
    {
LABEL_29:
      if ( !v4 )
        return v4;
    }
  }
  else
  {
    v4 = 87;
  }
LABEL_32:
  if ( (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"%s: failed: %d.", L"WriteQoSPoliciesToRegsitry", v4);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v17);
  }
  return v4;
}

```

## disassembly

```asm
0x180043aa0  mov     [rsp+arg_10], rbx
0x180043aa5  mov     [rsp+arg_18], rbp
0x180043aaa  push    rsi
0x180043aab  push    rdi
0x180043aac  push    r14
0x180043aae  sub     rsp, 840h
0x180043ab5  mov     rax, cs:__security_cookie
0x180043abc  xor     rax, rsp
0x180043abf  mov     [rsp+858h+var_28], rax
0x180043ac7  mov     rdi, rdx
0x180043aca  mov     r14, rcx
0x180043acd  xor     eax, eax
0x180043acf  lea     rcx, [rsp+858h+var_824]; void *
0x180043ad4  xor     edx, edx; Val
0x180043ad6  mov     [rsp+858h+var_828], eax
0x180043ada  mov     r8d, 7FCh; Size
0x180043ae0  call    memset_0
0x180043ae5  test    rdi, rdi
0x180043ae8  jz      loc_180043BF9
0x180043aee  test    r14, r14
0x180043af1  jz      loc_180043BF9
0x180043af7  xor     ebx, ebx
0x180043af9  xor     edx, edx
0x180043afb  mov     esi, 1
0x180043b00  mov     r9d, esi
0x180043b03  cmp     [rdi], edx
0x180043b05  jbe     short loc_180043B3F
0x180043b07  xor     ecx, ecx
0x180043b09  lea     r8, [rcx+rcx*2]
0x180043b0d  mov     eax, [rdi+r8*4+8]
0x180043b12  test    eax, eax
0x180043b14  jnz     short loc_180043B22
0x180043b16  cmp     [rdi+r8*4+4], ebx
0x180043b1b  jz      short loc_180043B31
0x180043b1d  xor     r9d, r9d
0x180043b20  jmp     short loc_180043B31
0x180043b22  cmp     eax, 1
0x180043b25  jnz     short loc_180043B31
0x180043b27  xor     eax, eax
0x180043b29  cmp     [rdi+r8*4+4], eax
0x180043b2e  cmovnz  esi, eax
0x180043b31  inc     edx
0x180043b33  inc     rcx
0x180043b36  cmp     edx, [rdi]
0x180043b38  jb      short loc_180043B09
0x180043b3a  test    r9d, r9d
0x180043b3d  jz      short loc_180043B62
0x180043b3f  lea     rdx, aTxbandwidthkbp; "TxBandwidthKbps"
0x180043b46  mov     rcx, r14; hKey
0x180043b49  call    cs:__imp_RegDeleteValueW
0x180043b4f  mov     ebx, eax
0x180043b51  cmp     eax, 2
0x180043b54  jnz     short loc_180043B5A
0x180043b56  xor     ebx, ebx
0x180043b58  jmp     short loc_180043B62
0x180043b5a  test    eax, eax
0x180043b5c  jnz     loc_180043BFE
0x180043b62  test    esi, esi
0x180043b64  jz      short loc_180043B85
0x180043b66  lea     rdx, aRxbandwidthkbp; "RxBandwidthKbps"
0x180043b6d  mov     rcx, r14; hKey
0x180043b70  call    cs:__imp_RegDeleteValueW
0x180043b76  mov     ebx, eax
0x180043b78  cmp     eax, 2
0x180043b7b  jnz     short loc_180043B81
0x180043b7d  xor     ebx, ebx
0x180043b7f  jmp     short loc_180043B85
0x180043b81  test    eax, eax
0x180043b83  jnz     short loc_180043BFE
0x180043b85  xor     ebp, ebp
0x180043b87  xor     esi, esi
0x180043b89  cmp     [rdi], esi
0x180043b8b  jbe     short loc_180043BF3
0x180043b8d  lea     rdx, [rsi+rsi*2]
0x180043b91  mov     ecx, [rdi+rdx*4+8]
0x180043b95  test    ecx, ecx
0x180043b97  jnz     short loc_180043BA2
0x180043b99  lea     rbp, aTxbandwidthkbp; "TxBandwidthKbps"
0x180043ba0  jmp     short loc_180043BB3
0x180043ba2  cmp     ecx, 1
0x180043ba5  lea     rax, aRxbandwidthkbp; "RxBandwidthKbps"
0x180043bac  cmovnz  rax, rbp
0x180043bb0  mov     rbp, rax
0x180043bb3  lea     rax, [rdi+4]
0x180043bb7  lea     rax, [rax+rdx*4]
0x180043bbb  cmp     dword ptr [rax], 0
0x180043bbe  jz      short loc_180043BED
0x180043bc0  cmp     dword ptr [rax], 1
0x180043bc3  jb      short loc_180043BF9
0x180043bc5  mov     [rsp+858h+cbData], 4; cbData
0x180043bcd  mov     r9d, 4; dwType
0x180043bd3  xor     r8d, r8d; Reserved
0x180043bd6  mov     [rsp+858h+lpData], rax; lpData
0x180043bdb  mov     rdx, rbp; lpValueName
0x180043bde  mov     rcx, r14; hKey
0x180043be1  call    cs:__imp_RegSetValueExW
0x180043be7  mov     ebx, eax
0x180043be9  test    eax, eax
0x180043beb  jnz     short loc_180043BFE
0x180043bed  inc     esi
0x180043bef  cmp     esi, [rdi]
0x180043bf1  jb      short loc_180043B8D
0x180043bf3  test    ebx, ebx
0x180043bf5  jz      short loc_180043C49
0x180043bf7  jmp     short loc_180043BFE
0x180043bf9  mov     ebx, 57h ; 'W'
0x180043bfe  cmp     qword ptr cs:xmmword_180078C50, 0
0x180043c06  jz      short loc_180043C49
0x180043c08  xor     eax, eax
0x180043c0a  lea     r8, aWriteqospolici; "WriteQoSPoliciesToRegsitry"
0x180043c11  mov     r9d, ebx
0x180043c14  mov     word ptr [rsp+858h+var_828], ax
0x180043c19  lea     rdx, aSFailedD; "%s: failed: %d."
0x180043c20  lea     rcx, [rsp+858h+var_828]
0x180043c25  call    FormatRRASErrorString
0x180043c2a  mov     rdx, qword ptr cs:xmmword_180078C50
0x180043c31  lea     r8, [rsp+858h+var_828]
0x180043c36  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180043c3d  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180043c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c49  mov     eax, ebx
0x180043c4b  mov     rcx, [rsp+858h+var_28]
0x180043c53  xor     rcx, rsp; StackCookie
0x180043c56  call    __security_check_cookie
0x180043c5b  lea     r11, [rsp+858h+var_18]
0x180043c63  mov     rbx, [r11+30h]
0x180043c67  mov     rbp, [r11+38h]
0x180043c6b  mov     rsp, r11
0x180043c6e  pop     r14
0x180043c70  pop     rdi
0x180043c71  pop     rsi
0x180043c72  retn
```
