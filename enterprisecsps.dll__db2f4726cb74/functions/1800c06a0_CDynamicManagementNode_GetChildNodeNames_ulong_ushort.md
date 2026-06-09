# CDynamicManagementNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800c06a0`
- end: `0x1800c07f5`
- name: `?GetChildNodeNames@CDynamicManagementNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `341`
- prototype: `int(CDynamicManagementNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800c03e4`
- `0x1800c06a0`
- `0x1800e3738`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800c078b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c078b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c07b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c07b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c07c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c07c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c075a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c075a`

## pseudocode

```c
__int64 __fastcall CDynamicManagementNode::GetChildNodeNames(
        CDynamicManagementNode *this,
        unsigned __int16 *a2,
        unsigned __int16 ***a3)
{
  int v5; // r9d
  int v6; // r9d
  unsigned int i; // ebx
  unsigned __int16 **v9; // rax
  unsigned __int16 **v10; // rdi
  __int64 v11; // rsi
  BSTR v12; // rax
  __int64 v13; // rbp
  OLECHAR *psz[11]; // [rsp+30h] [rbp-58h]

  if ( a2 && a3 )
  {
    *(_DWORD *)a2 = 0;
    *a3 = 0;
    v5 = *((_DWORD *)this + 11);
    if ( v5 )
    {
      v6 = v5 - 3;
      if ( !v6 )
        return DynamoGetAllContexts(*((const unsigned __int16 **)this + 17), a2, a3, (unsigned int *)a2);
      if ( v6 == 1 )
        return CDynamicManagementNode::GetAllContextChildNodes(
                 this,
                 *((const unsigned __int16 **)this + 17),
                 *((const unsigned __int16 **)this + 16),
                 (unsigned int *)a2,
                 a3);
      return (unsigned int)-2046820335;
    }
    else
    {
      psz[0] = L"NotificationsEnabled";
      psz[1] = L"ActiveList";
      psz[2] = (OLECHAR *)L"Contexts";
      psz[3] = L"AlertsEnabled";
      v9 = (unsigned __int16 **)CoTaskMemAlloc(0x20u);
      v10 = v9;
      if ( v9 )
      {
        v11 = 0;
        *(_OWORD *)v9 = 0;
        *((_OWORD *)v9 + 1) = 0;
        while ( 1 )
        {
          if ( (unsigned int)v11 >= 4 )
          {
            *a3 = v10;
            i = 0;
            *(_DWORD *)a2 = v11;
            return i;
          }
          v12 = SysAllocString(psz[v11]);
          v10[v11] = v12;
          if ( !v12 )
            break;
          v11 = (unsigned int)(v11 + 1);
        }
        v13 = 0;
        for ( i = -2147024882; (unsigned int)v13 < (unsigned int)v11; v13 = (unsigned int)(v13 + 1) )
          SysFreeString(v10[v13]);
        CoTaskMemFree(v10);
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
  return i;
}

```

## disassembly

```asm
0x1800c06a0  push    rbx
0x1800c06a2  push    rbp
0x1800c06a3  push    rsi
0x1800c06a4  push    rdi
0x1800c06a5  push    r14
0x1800c06a7  push    r15
0x1800c06a9  sub     rsp, 58h
0x1800c06ad  mov     r14, r8
0x1800c06b0  mov     r15, rdx
0x1800c06b3  test    rdx, rdx
0x1800c06b6  jz      loc_1800C07E0
0x1800c06bc  test    r8, r8
0x1800c06bf  jz      loc_1800C07E0
0x1800c06c5  mov     dword ptr [rdx], 0
0x1800c06cb  mov     qword ptr [r8], 0
0x1800c06d2  mov     r9d, [rcx+2Ch]
0x1800c06d6  test    r9d, r9d
0x1800c06d9  jz      short loc_1800C0725
0x1800c06db  sub     r9d, 3
0x1800c06df  jz      short loc_1800C0711
0x1800c06e1  cmp     r9d, 1
0x1800c06e5  jz      short loc_1800C06F1
0x1800c06e7  mov     ebx, 86000011h
0x1800c06ec  jmp     loc_1800C07E5
0x1800c06f1  mov     r8, [rcx+80h]; unsigned __int16 *
0x1800c06f8  mov     r9, r15; unsigned int *
0x1800c06fb  mov     rdx, [rcx+88h]; unsigned __int16 *
0x1800c0702  mov     [rsp+88h+var_68], r14; unsigned __int16 ***
0x1800c0707  call    ?GetAllContextChildNodes@CDynamicManagementNode@@IEAAJPEBG0PEAKPEAPEAPEAG@Z; CDynamicManagementNode::GetAllContextChildNodes(ushort const *,ushort const *,ulong *,ushort * * *)
0x1800c070c  jmp     loc_1800C07E7
0x1800c0711  mov     rcx, [rcx+88h]; unsigned __int16 *
0x1800c0718  mov     r9, r15; unsigned int *
0x1800c071b  call    ?DynamoGetAllContexts@@YAJPEBG0PEAPEAPEAGPEAK@Z; DynamoGetAllContexts(ushort const *,ushort const *,ushort * * *,ulong *)
0x1800c0720  jmp     loc_1800C07E7
0x1800c0725  lea     rax, aNotificationse; "NotificationsEnabled"
0x1800c072c  mov     ecx, 20h ; ' '; cb
0x1800c0731  mov     [rsp+88h+psz], rax
0x1800c0736  lea     rax, aActivelist; "ActiveList"
0x1800c073d  mov     [rsp+88h+var_50], rax
0x1800c0742  lea     rax, aContexts; "Contexts"
0x1800c0749  mov     [rsp+88h+var_48], rax
0x1800c074e  lea     rax, aAlertsenabled; "AlertsEnabled"
0x1800c0755  mov     [rsp+88h+var_40], rax
0x1800c075a  call    cs:__imp_CoTaskMemAlloc
0x1800c0761  nop     dword ptr [rax+rax+00h]
0x1800c0766  mov     rdi, rax
0x1800c0769  test    rax, rax
0x1800c076c  jnz     short loc_1800C0775
0x1800c076e  mov     ebx, 8007000Eh
0x1800c0773  jmp     short loc_1800C07E5
0x1800c0775  xorps   xmm0, xmm0
0x1800c0778  xor     esi, esi
0x1800c077a  movups  xmmword ptr [rax], xmm0
0x1800c077d  movups  xmmword ptr [rax+10h], xmm0
0x1800c0781  cmp     esi, 4
0x1800c0784  jnb     short loc_1800C07D6
0x1800c0786  mov     rcx, [rsp+rsi*8+88h+psz]; psz
0x1800c078b  call    cs:__imp_SysAllocString
0x1800c0792  nop     dword ptr [rax+rax+00h]
0x1800c0797  mov     [rdi+rsi*8], rax
0x1800c079b  test    rax, rax
0x1800c079e  jz      short loc_1800C07A4
0x1800c07a0  inc     esi
0x1800c07a2  jmp     short loc_1800C0781
0x1800c07a4  xor     ebp, ebp
0x1800c07a6  mov     ebx, 8007000Eh
0x1800c07ab  test    esi, esi
0x1800c07ad  jz      short loc_1800C07C5
0x1800c07af  mov     rcx, [rdi+rbp*8]; bstrString
0x1800c07b3  call    cs:__imp_SysFreeString
0x1800c07ba  nop     dword ptr [rax+rax+00h]
0x1800c07bf  inc     ebp
0x1800c07c1  cmp     ebp, esi
0x1800c07c3  jb      short loc_1800C07AF
0x1800c07c5  mov     rcx, rdi; pv
0x1800c07c8  call    cs:__imp_CoTaskMemFree
0x1800c07cf  nop     dword ptr [rax+rax+00h]
0x1800c07d4  jmp     short loc_1800C07E5
0x1800c07d6  mov     [r14], rdi
0x1800c07d9  xor     ebx, ebx
0x1800c07db  mov     [r15], esi
0x1800c07de  jmp     short loc_1800C07E5
0x1800c07e0  mov     ebx, 80070057h
0x1800c07e5  mov     eax, ebx
0x1800c07e7  add     rsp, 58h
0x1800c07eb  pop     r15
0x1800c07ed  pop     r14
0x1800c07ef  pop     rdi
0x1800c07f0  pop     rsi
0x1800c07f1  pop     rbp
0x1800c07f2  pop     rbx
0x1800c07f3  retn
```
