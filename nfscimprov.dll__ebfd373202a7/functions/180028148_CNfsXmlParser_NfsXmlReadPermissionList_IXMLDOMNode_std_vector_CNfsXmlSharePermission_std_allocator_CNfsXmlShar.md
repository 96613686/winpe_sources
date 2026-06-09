# CNfsXmlParser::NfsXmlReadPermissionList(IXMLDOMNode *,std::vector<CNfsXmlSharePermission *,std::allocator<CNfsXmlSharePermission *>> &)

- ea: `0x180028148`
- end: `0x18002832f`
- name: `?NfsXmlReadPermissionList@CNfsXmlParser@@AEAAJPEAUIXMLDOMNode@@AEAV?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180028338`

## callees

- `0x180001220`
- `0x180027790`
- `0x180027d18`
- `0x180028148`
- `0x18002921c`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800281db`
- `msvcrt!_wcsicmp` at `0x1800281db`
- `OLEAUT32!__imp_SysFreeString` at `0x18002831c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002831c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNfsXmlParser::NfsXmlReadPermissionList(__int64 a1, __int64 a2, _QWORD *a3)
{
  int PermissionEntry; // ebx
  unsigned int i; // r14d
  wchar_t *v7; // rax
  CNfsXmlSharePermission *v8; // rsi
  bool v9; // al
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v13; // [rsp+20h] [rbp-20h] BYREF
  CNfsXmlSharePermission *v14; // [rsp+28h] [rbp-18h] BYREF
  wchar_t *String1[2]; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF
  int v17; // [rsp+74h] [rbp+34h]
  int v18; // [rsp+78h] [rbp+38h] BYREF
  struct IXMLDOMNode *v19; // [rsp+88h] [rbp+48h] BYREF

  v17 = HIDWORD(a1);
  v16 = 0;
  String1[0] = 0;
  v13 = 0;
  v18 = 0;
  v19 = 0;
  PermissionEntry = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 80LL))(a2, &v16);
  if ( PermissionEntry >= 0 )
  {
    if ( v16 == 1 )
    {
      PermissionEntry = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)a2 + 56LL))(a2, String1);
      if ( PermissionEntry >= 0 && !_wcsicmp(String1[0], L"PermissionList") )
      {
        PermissionEntry = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v13);
        if ( PermissionEntry >= 0 )
          PermissionEntry = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 64LL))(v13, &v18);
        for ( i = 0; PermissionEntry >= 0 && (int)i < v18; ++i )
        {
          v7 = (wchar_t *)operator new(0x90u);
          String1[1] = v7;
          if ( v7 )
            v8 = CNfsXmlSharePermission::CNfsXmlSharePermission((CNfsXmlSharePermission *)v7);
          else
            v8 = 0;
          v14 = v8;
          if ( !v8 )
          {
            PermissionEntry = -2147024888;
            break;
          }
          PermissionEntry = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v13 + 56LL))(
                              v13,
                              i,
                              &v19);
          if ( PermissionEntry >= 0 )
          {
            PermissionEntry = CNfsXmlSharePermission::NfsXmlReadPermissionEntry(v8, v19);
            ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
            if ( PermissionEntry >= 0 )
            {
              v9 = (unsigned __int64)&v14 < a3[1] && *a3 <= (unsigned __int64)&v14;
              v10 = a3[2];
              if ( v9 )
              {
                v11 = ((__int64)&String1[-1] - *a3) >> 3;
                if ( a3[1] == v10 )
                  std::vector<CNfsXmlSharePermission *>::_Reserve(a3);
                *(_QWORD *)a3[1] = *(_QWORD *)(*a3 + 8 * v11);
              }
              else
              {
                if ( a3[1] == v10 )
                  std::vector<CNfsXmlSharePermission *>::_Reserve(a3);
                *(_QWORD *)a3[1] = v8;
              }
              a3[1] += 8LL;
            }
          }
          v19 = 0;
        }
      }
    }
    else
    {
      PermissionEntry = -2147024809;
    }
  }
  SysFreeString(String1[0]);
  return (unsigned int)PermissionEntry;
}

```

## disassembly

```asm
0x180028148  mov     [rsp-28h+arg_0], rcx
0x18002814d  push    rbp
0x18002814e  push    rbx
0x18002814f  push    rsi
0x180028150  push    rdi
0x180028151  push    r14
0x180028153  mov     rbp, rsp
0x180028156  sub     rsp, 40h
0x18002815a  mov     rdi, r8
0x18002815d  mov     rsi, rdx
0x180028160  mov     dword ptr [rbp+arg_0], 0
0x180028167  mov     [rbp+String1], 0
0x18002816f  mov     [rbp+var_20], 0
0x180028177  mov     [rbp+arg_8], 0
0x18002817e  mov     [rbp+arg_18], 0
0x180028186  mov     rax, [rdx]
0x180028189  lea     rdx, [rbp+arg_0]
0x18002818d  mov     rcx, rsi
0x180028190  mov     rax, [rax+50h]
0x180028194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028199  mov     ebx, eax
0x18002819b  test    eax, eax
0x18002819d  js      loc_180028318
0x1800281a3  cmp     dword ptr [rbp+arg_0], 1
0x1800281a7  jz      short loc_1800281B3
0x1800281a9  mov     ebx, 80070057h
0x1800281ae  jmp     loc_180028318
0x1800281b3  mov     rax, [rsi]
0x1800281b6  lea     rdx, [rbp+String1]
0x1800281ba  mov     rcx, rsi
0x1800281bd  mov     rax, [rax+38h]
0x1800281c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281c6  mov     ebx, eax
0x1800281c8  test    eax, eax
0x1800281ca  js      loc_180028318
0x1800281d0  lea     rdx, aPermissionlist; "PermissionList"
0x1800281d7  mov     rcx, [rbp+String1]; String1
0x1800281db  call    cs:__imp__wcsicmp
0x1800281e1  test    eax, eax
0x1800281e3  jnz     loc_180028318
0x1800281e9  mov     rax, [rsi]
0x1800281ec  lea     rdx, [rbp+var_20]
0x1800281f0  mov     rcx, rsi
0x1800281f3  mov     rax, [rax+60h]
0x1800281f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281fc  mov     ebx, eax
0x1800281fe  test    eax, eax
0x180028200  js      short loc_180028218
0x180028202  mov     rcx, [rbp+var_20]
0x180028206  mov     rax, [rcx]
0x180028209  lea     rdx, [rbp+arg_8]
0x18002820d  mov     rax, [rax+40h]
0x180028211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028216  mov     ebx, eax
0x180028218  xor     r14d, r14d
0x18002821b  test    ebx, ebx
0x18002821d  js      loc_180028318
0x180028223  cmp     r14d, [rbp+arg_8]
0x180028227  jge     loc_180028318
0x18002822d  mov     ecx, 90h; Size
0x180028232  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028237  mov     [rbp+var_8], rax
0x18002823b  test    rax, rax
0x18002823e  jz      short loc_18002824D
0x180028240  mov     rcx, rax; this
0x180028243  call    ??0CNfsXmlSharePermission@@QEAA@XZ; CNfsXmlSharePermission::CNfsXmlSharePermission(void)
0x180028248  mov     rsi, rax
0x18002824b  jmp     short loc_18002824F
0x18002824d  xor     esi, esi
0x18002824f  mov     [rbp+var_18], rsi
0x180028253  test    rsi, rsi
0x180028256  jz      loc_180028313
0x18002825c  mov     rcx, [rbp+var_20]
0x180028260  mov     rax, [rcx]
0x180028263  lea     r8, [rbp+arg_18]
0x180028267  mov     edx, r14d
0x18002826a  mov     rax, [rax+38h]
0x18002826e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028273  mov     ebx, eax
0x180028275  test    eax, eax
0x180028277  js      loc_180028303
0x18002827d  mov     rdx, [rbp+arg_18]; struct IXMLDOMNode *
0x180028281  mov     rcx, rsi; this
0x180028284  call    ?NfsXmlReadPermissionEntry@CNfsXmlSharePermission@@QEAAJPEAUIXMLDOMNode@@@Z; CNfsXmlSharePermission::NfsXmlReadPermissionEntry(IXMLDOMNode *)
0x180028289  mov     ebx, eax
0x18002828b  mov     rcx, [rbp+arg_18]
0x18002828f  mov     rax, [rcx]
0x180028292  mov     rax, [rax+10h]
0x180028296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002829b  test    ebx, ebx
0x18002829d  js      short loc_180028303
0x18002829f  lea     rax, [rbp+var_18]
0x1800282a3  cmp     rax, [rdi+8]
0x1800282a7  jnb     short loc_1800282B6
0x1800282a9  lea     rax, [rbp+var_18]
0x1800282ad  cmp     [rdi], rax
0x1800282b0  ja      short loc_1800282B6
0x1800282b2  mov     al, 1
0x1800282b4  jmp     short loc_1800282B8
0x1800282b6  xor     al, al
0x1800282b8  mov     rcx, [rdi+10h]
0x1800282bc  test    al, al
0x1800282be  jz      short loc_1800282E9
0x1800282c0  lea     rsi, [rbp+var_18]
0x1800282c4  sub     rsi, [rdi]
0x1800282c7  sar     rsi, 3
0x1800282cb  cmp     [rdi+8], rcx
0x1800282cf  jnz     short loc_1800282D9
0x1800282d1  mov     rcx, rdi
0x1800282d4  call    ?_Reserve@?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@IEAAX_K@Z; std::vector<CNfsXmlSharePermission *>::_Reserve(unsigned __int64)
0x1800282d9  mov     rax, [rdi]
0x1800282dc  mov     rcx, [rdi+8]
0x1800282e0  mov     rax, [rax+rsi*8]
0x1800282e4  mov     [rcx], rax
0x1800282e7  jmp     short loc_1800282FE
0x1800282e9  cmp     [rdi+8], rcx
0x1800282ed  jnz     short loc_1800282F7
0x1800282ef  mov     rcx, rdi
0x1800282f2  call    ?_Reserve@?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@IEAAX_K@Z; std::vector<CNfsXmlSharePermission *>::_Reserve(unsigned __int64)
0x1800282f7  mov     rax, [rdi+8]
0x1800282fb  mov     [rax], rsi
0x1800282fe  add     qword ptr [rdi+8], 8
0x180028303  mov     [rbp+arg_18], 0
0x18002830b  inc     r14d
0x18002830e  jmp     loc_18002821B
0x180028313  mov     ebx, 80070008h
0x180028318  mov     rcx, [rbp+String1]; bstrString
0x18002831c  call    cs:__imp_SysFreeString
0x180028322  mov     eax, ebx
0x180028324  add     rsp, 40h
0x180028328  pop     r14
0x18002832a  pop     rdi
0x18002832b  pop     rsi
0x18002832c  pop     rbx
0x18002832d  pop     rbp
0x18002832e  retn
```
