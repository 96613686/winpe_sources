# CNoPinList::_AddPath(ushort const *)

- ea: `0x18003b00c`
- end: `0x18003b1a7`
- name: `?_AddPath@CNoPinList@@AEAAJPEBG@Z`
- size: `411`
- prototype: `int(CNoPinList *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003b254`

## callees

- `0x180003d60`
- `0x18000c1e8`
- `0x18001182c`
- `0x18003ab30`
- `0x18003ab58`
- `0x18003b00c`
- `0x18003b1b0`
- `0x18003b200`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18003b045`
- `SHLWAPI!PathIsUNCW` at `0x18003b045`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003b133`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003b133`

## pseudocode

```c
__int64 __fastcall CNoPinList::_AddPath(LPCWSTR ***this, const unsigned __int16 *a2)
{
  int v4; // edi
  int v5; // eax
  LPCWSTR **v6; // rbp
  unsigned int v7; // edx
  const unsigned __int16 *NextPathComponent; // r15
  unsigned __int16 *v9; // rsi
  unsigned __int16 v10; // r14
  struct CNoPinList::CNode *Child; // rax
  LPCWSTR *v12; // rax
  LPCWSTR *v13; // rbx
  int v14; // eax
  unsigned int v15; // edx
  LPCWSTR **i; // rsi
  LPCWSTR *v17; // r14
  int v18; // eax
  CNoPinList::CNode *v19; // rcx
  int v21[4]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v22[264]; // [rsp+30h] [rbp-248h] BYREF

  v4 = -2147024735;
  if ( PathIsUNCW(a2) )
  {
    v5 = StringCchCopyW(v22, 0x104u, a2);
    if ( v5 < 0 )
    {
      if ( v5 == -2147024774 )
        return (unsigned int)-2147024735;
      return (unsigned int)v5;
    }
    v6 = *this;
    v21[0] = 0;
    v4 = 0;
    NextPathComponent = CNoPinList::CNode::_FindNextPathComponent(v22, v21);
    if ( *NextPathComponent )
    {
      v9 = (unsigned __int16 *)&NextPathComponent[v21[0]];
      v10 = *v9;
      *v9 = 0;
      Child = CNoPinList::CNode::_FindChild((CNoPinList::CNode *)v6, NextPathComponent);
      if ( Child )
      {
        *v9 = v10;
        if ( *((_QWORD *)Child + 1) )
          return (unsigned int)CNoPinList::CNode::AddPath(Child, v9);
      }
      else
      {
        v4 = -2147024882;
        v12 = (LPCWSTR *)operator new(0x18u);
        v13 = v12;
        if ( v12 )
        {
          *v12 = 0;
          v12[1] = 0;
          v12[2] = 0;
          v14 = LocalAllocString((unsigned __int16 **)v12, NextPathComponent);
          *v9 = v10;
          if ( v14 && (v4 = CNoPinList::CNode::AddPath((CNoPinList::CNode *)v13, v9), v4 >= 0) )
          {
            for ( i = v6 + 1; ; i = (LPCWSTR **)(v17 + 2) )
            {
              v17 = *i;
              if ( !*i )
                break;
              v18 = lstrcmpiW(*v13, *v17);
              if ( !v18 )
                return (unsigned int)v4;
              if ( v18 < 0 )
                break;
            }
            v13[2] = (LPCWSTR)*i;
            *i = v13;
          }
          else
          {
            CNoPinList::CNode::`scalar deleting destructor'((CNoPinList::CNode *)v13, v15);
          }
        }
      }
    }
    else
    {
      v19 = (CNoPinList::CNode *)v6[1];
      if ( v19 )
        CNoPinList::CNode::`scalar deleting destructor'(v19, v7);
      v6[1] = 0;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003b00c  mov     [rsp+arg_10], rbx
0x18003b011  mov     [rsp+arg_18], rbp
0x18003b016  push    rsi
0x18003b017  push    rdi
0x18003b018  push    r12
0x18003b01a  push    r14
0x18003b01c  push    r15
0x18003b01e  sub     rsp, 250h
0x18003b025  mov     rax, cs:__security_cookie
0x18003b02c  xor     rax, rsp
0x18003b02f  mov     [rsp+278h+var_38], rax
0x18003b037  mov     rbp, rcx
0x18003b03a  mov     rbx, rdx
0x18003b03d  mov     rcx, rdx; pszPath
0x18003b040  mov     edi, 800700A1h
0x18003b045  call    cs:__imp_PathIsUNCW
0x18003b04b  xor     r12d, r12d
0x18003b04e  test    eax, eax
0x18003b050  jz      loc_18003B179
0x18003b056  mov     r8, rbx; unsigned __int16 *
0x18003b059  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x18003b05e  mov     edx, 104h; unsigned __int64
0x18003b063  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b068  test    eax, eax
0x18003b06a  js      loc_18003B16F
0x18003b070  mov     rbp, [rbp+0]
0x18003b074  lea     rdx, [rsp+278h+var_258]; int *
0x18003b079  lea     rcx, [rsp+278h+var_248]; unsigned __int16 *
0x18003b07e  mov     [rsp+278h+var_258], r12d
0x18003b083  mov     edi, r12d
0x18003b086  call    ?_FindNextPathComponent@CNode@CNoPinList@@CAPEBGPEBGPEAH@Z; CNoPinList::CNode::_FindNextPathComponent(ushort const *,int *)
0x18003b08b  mov     r15, rax
0x18003b08e  cmp     [rax], r12w
0x18003b092  jz      loc_18003B15B
0x18003b098  movsxd  rax, [rsp+278h+var_258]
0x18003b09d  mov     rdx, r15; unsigned __int16 *
0x18003b0a0  mov     rcx, rbp; this
0x18003b0a3  lea     rsi, [r15+rax*2]
0x18003b0a7  movzx   r14d, word ptr [rsi]
0x18003b0ab  mov     [rsi], r12w
0x18003b0af  call    ?_FindChild@CNode@CNoPinList@@AEBAPEAV12@PEBG@Z; CNoPinList::CNode::_FindChild(ushort const *)
0x18003b0b4  test    rax, rax
0x18003b0b7  jz      short loc_18003B0D7
0x18003b0b9  mov     [rsi], r14w
0x18003b0bd  cmp     [rax+8], r12
0x18003b0c1  jz      loc_18003B179
0x18003b0c7  mov     rdx, rsi; unsigned __int16 *
0x18003b0ca  mov     rcx, rax; this
0x18003b0cd  call    ?AddPath@CNode@CNoPinList@@QEAAJPEAG@Z; CNoPinList::CNode::AddPath(ushort *)
0x18003b0d2  jmp     loc_18003B177
0x18003b0d7  mov     ecx, 18h; Size
0x18003b0dc  mov     edi, 8007000Eh
0x18003b0e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b0e6  mov     rbx, rax
0x18003b0e9  test    rax, rax
0x18003b0ec  jz      loc_18003B179
0x18003b0f2  mov     rdx, r15; unsigned __int16 *
0x18003b0f5  mov     [rax], r12
0x18003b0f8  mov     rcx, rax; unsigned __int16 **
0x18003b0fb  mov     [rax+8], r12
0x18003b0ff  mov     [rax+10h], r12
0x18003b103  call    ?LocalAllocString@@YAHPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x18003b108  mov     [rsi], r14w
0x18003b10c  test    eax, eax
0x18003b10e  jz      short loc_18003B151
0x18003b110  mov     rdx, rsi; unsigned __int16 *
0x18003b113  mov     rcx, rbx; this
0x18003b116  call    ?AddPath@CNode@CNoPinList@@QEAAJPEAG@Z; CNoPinList::CNode::AddPath(ushort *)
0x18003b11b  mov     edi, eax
0x18003b11d  test    eax, eax
0x18003b11f  js      short loc_18003B151
0x18003b121  lea     rsi, [rbp+8]
0x18003b125  mov     r14, [rsi]
0x18003b128  test    r14, r14
0x18003b12b  jz      short loc_18003B145
0x18003b12d  mov     rdx, [r14]; lpString2
0x18003b130  mov     rcx, [rbx]; lpString1
0x18003b133  call    cs:__imp_lstrcmpiW
0x18003b139  test    eax, eax
0x18003b13b  jz      short loc_18003B179
0x18003b13d  js      short loc_18003B145
0x18003b13f  lea     rsi, [r14+10h]
0x18003b143  jmp     short loc_18003B125
0x18003b145  mov     rax, [rsi]
0x18003b148  mov     [rbx+10h], rax
0x18003b14c  mov     [rsi], rbx
0x18003b14f  jmp     short loc_18003B179
0x18003b151  mov     rcx, rbx; this
0x18003b154  call    ??_GCNode@CNoPinList@@QEAAPEAXI@Z; CNoPinList::CNode::`scalar deleting destructor'(uint)
0x18003b159  jmp     short loc_18003B179
0x18003b15b  mov     rcx, [rbp+8]; this
0x18003b15f  test    rcx, rcx
0x18003b162  jz      short loc_18003B169
0x18003b164  call    ??_GCNode@CNoPinList@@QEAAPEAXI@Z; CNoPinList::CNode::`scalar deleting destructor'(uint)
0x18003b169  mov     [rbp+8], r12
0x18003b16d  jmp     short loc_18003B179
0x18003b16f  cmp     eax, 8007007Ah
0x18003b174  cmovz   eax, edi
0x18003b177  mov     edi, eax
0x18003b179  mov     eax, edi
0x18003b17b  mov     rcx, [rsp+278h+var_38]
0x18003b183  xor     rcx, rsp; StackCookie
0x18003b186  call    __security_check_cookie
0x18003b18b  lea     r11, [rsp+278h+var_28]
0x18003b193  mov     rbx, [r11+40h]
0x18003b197  mov     rbp, [r11+48h]
0x18003b19b  mov     rsp, r11
0x18003b19e  pop     r15
0x18003b1a0  pop     r14
0x18003b1a2  pop     r12
0x18003b1a4  pop     rdi
0x18003b1a5  pop     rsi
0x18003b1a6  retn
```
