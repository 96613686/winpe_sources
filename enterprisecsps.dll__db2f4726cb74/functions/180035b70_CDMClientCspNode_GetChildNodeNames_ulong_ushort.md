# CDMClientCspNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180035b70`
- end: `0x180035cdb`
- name: `?GetChildNodeNames@CDMClientCspNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `363`
- prototype: `__int64 __fastcall(CDMClientCspNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x180035b70`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180035c4b`
- `OLEAUT32!__imp_SysAllocString` at `0x180035c4b`
- `OLEAUT32!__imp_SysFreeString` at `0x180035c86`
- `OLEAUT32!__imp_SysFreeString` at `0x180035c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035c04`

## string_xrefs

- `0x180035ba0`: `UpdateManagementServiceAddress`

## pseudocode

```c
__int64 __fastcall CDMClientCspNode::GetChildNodeNames(
        CDMClientCspNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  unsigned int v5; // edi
  __int64 v6; // rcx
  unsigned int v7; // eax
  int v8; // ebx
  size_t v9; // rbp
  unsigned __int16 **v10; // rax
  unsigned __int16 **v11; // rsi
  __int64 v12; // rbp
  int i; // r14d
  const OLECHAR *v14; // rcx
  BSTR v15; // rax
  __int64 j; // rbp
  OLECHAR *v17; // rcx
  OLECHAR *psz[4]; // [rsp+20h] [rbp-48h]
  SIZE_T cb; // [rsp+78h] [rbp+10h] BYREF

  psz[0] = L"Provider";
  psz[1] = L"Unenroll";
  psz[2] = L"UpdateManagementServiceAddress";
  if ( a2 && a3 )
  {
    v5 = 0;
    *a2 = 0;
    v6 = 0;
    *a3 = 0;
    LODWORD(cb) = 0;
    do
    {
      v7 = v5 + 1;
      if ( !psz[v6] )
        v7 = v5;
      ++v6;
      v5 = v7;
    }
    while ( v6 != 3 );
    v8 = ULongLongToULong(8LL * v7, (unsigned int *)&cb);
    if ( v8 >= 0 )
    {
      v9 = (unsigned int)cb;
      v10 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
      v11 = v10;
      if ( v10 )
      {
        memset_0(v10, 0, v9);
        v12 = 0;
        for ( i = 0; i < 3; ++i )
        {
          if ( (unsigned int)v12 >= v5 )
            goto LABEL_19;
          v14 = psz[i];
          if ( v14 )
          {
            v15 = SysAllocString(v14);
            v11[v12] = v15;
            if ( !v15 )
            {
              v8 = -2147024882;
              goto LABEL_20;
            }
            v12 = (unsigned int)(v12 + 1);
          }
        }
        if ( (_DWORD)v12 == v5 )
        {
          *a2 = v12;
          *a3 = v11;
          return (unsigned int)v8;
        }
LABEL_19:
        v8 = -2147418113;
LABEL_20:
        for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
        {
          v17 = v11[j];
          if ( v17 )
          {
            SysFreeString(v17);
            v11[j] = 0;
          }
        }
        CoTaskMemFree(v11);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180035b70  mov     r11, rsp
0x180035b73  mov     [r11+8], rbx
0x180035b77  mov     [r11+18h], rbp
0x180035b7b  push    rsi
0x180035b7c  push    rdi
0x180035b7d  push    r12
0x180035b7f  push    r14
0x180035b81  push    r15
0x180035b83  sub     rsp, 40h
0x180035b87  lea     rax, aProvider; "Provider"
0x180035b8e  mov     r15, r8
0x180035b91  mov     [r11-48h], rax
0x180035b95  lea     rax, aUnenroll; "Unenroll"
0x180035b9c  mov     [r11-40h], rax
0x180035ba0  lea     rax, aUpdatemanageme; "UpdateManagementServiceAddress"
0x180035ba7  mov     [r11-38h], rax
0x180035bab  mov     r12, rdx
0x180035bae  test    rdx, rdx
0x180035bb1  jz      loc_180035CBA
0x180035bb7  test    r8, r8
0x180035bba  jz      loc_180035CBA
0x180035bc0  xor     edi, edi
0x180035bc2  mov     [rdx], edi
0x180035bc4  xor     ecx, ecx
0x180035bc6  mov     [r8], rdi
0x180035bc9  mov     dword ptr [rsp+68h+cb], edi
0x180035bcd  cmp     [rsp+rcx*8+68h+psz], 0
0x180035bd3  lea     eax, [rdi+1]
0x180035bd6  cmovz   eax, edi
0x180035bd9  inc     rcx
0x180035bdc  mov     edi, eax
0x180035bde  cmp     rcx, 3
0x180035be2  jnz     short loc_180035BCD
0x180035be4  mov     ecx, edi
0x180035be6  lea     rdx, [rsp+68h+cb]; unsigned int *
0x180035beb  shl     rcx, 3; unsigned __int64
0x180035bef  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180035bf4  mov     ebx, eax
0x180035bf6  test    eax, eax
0x180035bf8  js      loc_180035CBF
0x180035bfe  mov     ebp, dword ptr [rsp+68h+cb]
0x180035c02  mov     ecx, ebp; cb
0x180035c04  call    cs:__imp_CoTaskMemAlloc
0x180035c0b  nop     dword ptr [rax+rax+00h]
0x180035c10  mov     rsi, rax
0x180035c13  test    rax, rax
0x180035c16  jnz     short loc_180035C22
0x180035c18  mov     ebx, 8007000Eh
0x180035c1d  jmp     loc_180035CBF
0x180035c22  mov     r8, rbp; Size
0x180035c25  xor     edx, edx; Val
0x180035c27  mov     rcx, rsi; void *
0x180035c2a  call    memset_0
0x180035c2f  xor     ebp, ebp
0x180035c31  xor     r14d, r14d
0x180035c34  cmp     r14d, 3
0x180035c38  jge     short loc_180035C6E
0x180035c3a  cmp     ebp, edi
0x180035c3c  jnb     short loc_180035C72
0x180035c3e  movsxd  rax, r14d
0x180035c41  mov     rcx, [rsp+rax*8+68h+psz]; psz
0x180035c46  test    rcx, rcx
0x180035c49  jz      short loc_180035C62
0x180035c4b  call    cs:__imp_SysAllocString
0x180035c52  nop     dword ptr [rax+rax+00h]
0x180035c57  mov     [rsi+rbp*8], rax
0x180035c5b  test    rax, rax
0x180035c5e  jz      short loc_180035C67
0x180035c60  inc     ebp
0x180035c62  inc     r14d
0x180035c65  jmp     short loc_180035C34
0x180035c67  mov     ebx, 8007000Eh
0x180035c6c  jmp     short loc_180035C77
0x180035c6e  cmp     ebp, edi
0x180035c70  jz      short loc_180035CB1
0x180035c72  mov     ebx, 8000FFFFh
0x180035c77  xor     ebp, ebp
0x180035c79  test    edi, edi
0x180035c7b  jz      short loc_180035CA0
0x180035c7d  mov     rcx, [rsi+rbp*8]; bstrString
0x180035c81  test    rcx, rcx
0x180035c84  jz      short loc_180035C9A
0x180035c86  call    cs:__imp_SysFreeString
0x180035c8d  nop     dword ptr [rax+rax+00h]
0x180035c92  mov     qword ptr [rsi+rbp*8], 0
0x180035c9a  inc     ebp
0x180035c9c  cmp     ebp, edi
0x180035c9e  jb      short loc_180035C7D
0x180035ca0  mov     rcx, rsi; pv
0x180035ca3  call    cs:__imp_CoTaskMemFree
0x180035caa  nop     dword ptr [rax+rax+00h]
0x180035caf  jmp     short loc_180035CBF
0x180035cb1  mov     [r12], ebp
0x180035cb5  mov     [r15], rsi
0x180035cb8  jmp     short loc_180035CBF
0x180035cba  mov     ebx, 80070057h
0x180035cbf  lea     r11, [rsp+68h+var_28]
0x180035cc4  mov     eax, ebx
0x180035cc6  mov     rbx, [r11+30h]
0x180035cca  mov     rbp, [r11+40h]
0x180035cce  mov     rsp, r11
0x180035cd1  pop     r15
0x180035cd3  pop     r14
0x180035cd5  pop     r12
0x180035cd7  pop     rdi
0x180035cd8  pop     rsi
0x180035cd9  retn
```
