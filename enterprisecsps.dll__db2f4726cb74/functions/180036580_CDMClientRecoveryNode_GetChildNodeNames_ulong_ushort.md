# CDMClientRecoveryNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180036580`
- end: `0x180036729`
- name: `?GetChildNodeNames@CDMClientRecoveryNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `425`
- prototype: `__int64 __fastcall(CDMClientRecoveryNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x180036580`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003668b`
- `OLEAUT32!__imp_SysAllocString` at `0x18003668b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800366c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180036701`
- `OLEAUT32!__imp_SysFreeString` at `0x1800366c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180036701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800366e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036644`

## pseudocode

```c
__int64 __fastcall CDMClientRecoveryNode::GetChildNodeNames(
        CDMClientRecoveryNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  int v3; // r9d
  int v6; // r9d
  int v7; // r9d
  int v8; // ebx
  unsigned int v9; // edi
  __int64 v10; // rcx
  unsigned int v11; // eax
  size_t v12; // rbp
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // rsi
  __int64 v15; // rbp
  int i; // r14d
  const OLECHAR *v17; // rcx
  BSTR v18; // rax
  __int64 j; // rbp
  OLECHAR *v20; // rcx
  OLECHAR *psz[4]; // [rsp+20h] [rbp-48h]
  SIZE_T cb; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 11);
  psz[0] = L"AllowRecovery";
  psz[1] = L"InitiateRecovery";
  psz[2] = L"RecoveryStatus";
  v6 = v3 - 86;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 && (unsigned int)(v7 - 1) >= 2 )
      v8 = -2147418113;
    else
      v8 = -2046820335;
  }
  else if ( a2 && a3 )
  {
    v9 = 0;
    *a2 = 0;
    v10 = 0;
    *a3 = 0;
    LODWORD(cb) = 0;
    do
    {
      v11 = v9 + 1;
      if ( !psz[v10] )
        v11 = v9;
      ++v10;
      v9 = v11;
    }
    while ( v10 != 3 );
    v8 = ULongLongToULong(8LL * v11, (unsigned int *)&cb);
    if ( v8 >= 0 )
    {
      v12 = (unsigned int)cb;
      v13 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
      v14 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, v12);
        v15 = 0;
        for ( i = 0; i < 3; ++i )
        {
          if ( (unsigned int)v15 >= v9 )
            goto LABEL_24;
          v17 = psz[i];
          if ( v17 )
          {
            v18 = SysAllocString(v17);
            v14[v15] = v18;
            if ( !v18 )
            {
              v8 = -2147024882;
              goto LABEL_25;
            }
            v15 = (unsigned int)(v15 + 1);
          }
        }
        if ( (_DWORD)v15 == v9 )
        {
          *a2 = v15;
          *a3 = v14;
          goto LABEL_32;
        }
LABEL_24:
        v8 = -2147418113;
LABEL_25:
        for ( j = 0; (unsigned int)j < v9; j = (unsigned int)(j + 1) )
        {
          v20 = v14[j];
          if ( v20 )
          {
            SysFreeString(v20);
            v14[j] = 0;
          }
        }
        CoTaskMemFree(v14);
      }
      else
      {
        v8 = -2147024882;
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_32:
  SysFreeString(0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036580  mov     r11, rsp
0x180036583  mov     [r11+10h], rbx
0x180036587  mov     [r11+18h], rbp
0x18003658b  push    rsi
0x18003658c  push    rdi
0x18003658d  push    r12
0x18003658f  push    r14
0x180036591  push    r15
0x180036593  sub     rsp, 40h
0x180036597  mov     r9d, [rcx+2Ch]
0x18003659b  lea     rax, aAllowrecovery; "AllowRecovery"
0x1800365a2  mov     [r11-48h], rax
0x1800365a6  lea     rax, aInitiaterecove; "InitiateRecovery"
0x1800365ad  mov     [r11-40h], rax
0x1800365b1  lea     rax, aRecoverystatus; "RecoveryStatus"
0x1800365b8  mov     [r11-38h], rax
0x1800365bc  mov     r15, r8
0x1800365bf  mov     r12, rdx
0x1800365c2  sub     r9d, 56h ; 'V'
0x1800365c6  jz      short loc_1800365EE
0x1800365c8  sub     r9d, 1
0x1800365cc  jz      short loc_1800365E4
0x1800365ce  sub     r9d, 1
0x1800365d2  jz      short loc_1800365E4
0x1800365d4  cmp     r9d, 1
0x1800365d8  jz      short loc_1800365E4
0x1800365da  mov     ebx, 8000FFFFh
0x1800365df  jmp     loc_1800366FF
0x1800365e4  mov     ebx, 86000011h
0x1800365e9  jmp     loc_1800366FF
0x1800365ee  test    r12, r12
0x1800365f1  jz      loc_1800366FA
0x1800365f7  test    r15, r15
0x1800365fa  jz      loc_1800366FA
0x180036600  xor     edi, edi
0x180036602  mov     [rdx], edi
0x180036604  xor     ecx, ecx
0x180036606  mov     [r8], rdi
0x180036609  mov     dword ptr [rsp+68h+cb], edi
0x18003660d  cmp     [rsp+rcx*8+68h+psz], 0
0x180036613  lea     eax, [rdi+1]
0x180036616  cmovz   eax, edi
0x180036619  inc     rcx
0x18003661c  mov     edi, eax
0x18003661e  cmp     rcx, 3
0x180036622  jnz     short loc_18003660D
0x180036624  mov     ecx, edi
0x180036626  lea     rdx, [rsp+68h+cb]; unsigned int *
0x18003662b  shl     rcx, 3; unsigned __int64
0x18003662f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180036634  mov     ebx, eax
0x180036636  test    eax, eax
0x180036638  js      loc_1800366FF
0x18003663e  mov     ebp, dword ptr [rsp+68h+cb]
0x180036642  mov     ecx, ebp; cb
0x180036644  call    cs:__imp_CoTaskMemAlloc
0x18003664b  nop     dword ptr [rax+rax+00h]
0x180036650  mov     rsi, rax
0x180036653  test    rax, rax
0x180036656  jnz     short loc_180036662
0x180036658  mov     ebx, 8007000Eh
0x18003665d  jmp     loc_1800366FF
0x180036662  mov     r8, rbp; Size
0x180036665  xor     edx, edx; Val
0x180036667  mov     rcx, rsi; void *
0x18003666a  call    memset_0
0x18003666f  xor     ebp, ebp
0x180036671  xor     r14d, r14d
0x180036674  cmp     r14d, 3
0x180036678  jge     short loc_1800366AE
0x18003667a  cmp     ebp, edi
0x18003667c  jnb     short loc_1800366B2
0x18003667e  movsxd  rax, r14d
0x180036681  mov     rcx, [rsp+rax*8+68h+psz]; psz
0x180036686  test    rcx, rcx
0x180036689  jz      short loc_1800366A2
0x18003668b  call    cs:__imp_SysAllocString
0x180036692  nop     dword ptr [rax+rax+00h]
0x180036697  mov     [rsi+rbp*8], rax
0x18003669b  test    rax, rax
0x18003669e  jz      short loc_1800366A7
0x1800366a0  inc     ebp
0x1800366a2  inc     r14d
0x1800366a5  jmp     short loc_180036674
0x1800366a7  mov     ebx, 8007000Eh
0x1800366ac  jmp     short loc_1800366B7
0x1800366ae  cmp     ebp, edi
0x1800366b0  jz      short loc_1800366F1
0x1800366b2  mov     ebx, 8000FFFFh
0x1800366b7  xor     ebp, ebp
0x1800366b9  test    edi, edi
0x1800366bb  jz      short loc_1800366E0
0x1800366bd  mov     rcx, [rsi+rbp*8]; bstrString
0x1800366c1  test    rcx, rcx
0x1800366c4  jz      short loc_1800366DA
0x1800366c6  call    cs:__imp_SysFreeString
0x1800366cd  nop     dword ptr [rax+rax+00h]
0x1800366d2  mov     qword ptr [rsi+rbp*8], 0
0x1800366da  inc     ebp
0x1800366dc  cmp     ebp, edi
0x1800366de  jb      short loc_1800366BD
0x1800366e0  mov     rcx, rsi; pv
0x1800366e3  call    cs:__imp_CoTaskMemFree
0x1800366ea  nop     dword ptr [rax+rax+00h]
0x1800366ef  jmp     short loc_1800366FF
0x1800366f1  mov     [r12], ebp
0x1800366f5  mov     [r15], rsi
0x1800366f8  jmp     short loc_1800366FF
0x1800366fa  mov     ebx, 80070057h
0x1800366ff  xor     ecx, ecx; bstrString
0x180036701  call    cs:__imp_SysFreeString
0x180036708  nop     dword ptr [rax+rax+00h]
0x18003670d  lea     r11, [rsp+68h+var_28]
0x180036712  mov     eax, ebx
0x180036714  mov     rbx, [r11+38h]
0x180036718  mov     rbp, [r11+40h]
0x18003671c  mov     rsp, r11
0x18003671f  pop     r15
0x180036721  pop     r14
0x180036723  pop     r12
0x180036725  pop     rdi
0x180036726  pop     rsi
0x180036727  retn
```
