# AslpEnvResolveVars

- ea: `0x140018184`
- end: `0x1400184c5`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140017cb8`

## callees

- `0x140002630`
- `0x1400135a4`
- `0x1400141e8`
- `0x1400151b0`
- `0x140018184`

## string_xrefs

- `0x140018427`: `RtlStringCchCopyW failed [%x]`
- `0x14001843a`: `RtlStringCchCopyW failed [%x]`
- `0x140018493`: `RtlStringCchCopyW failed [%x]`
- `0x14001844e`: `ResolvedPath is NULL or zero size [%#x]`
- `0x140018318`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        const wchar_t *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  unsigned __int64 v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  unsigned __int16 *v11; // rdi
  __int64 v12; // r12
  __int64 v14; // r15
  unsigned int v15; // eax
  unsigned __int16 v16; // cx
  unsigned __int64 i; // rdi
  unsigned __int16 v18; // ax
  int v19; // eax
  __int64 v20; // r11
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v28; // [rsp+20h] [rbp-48h]
  const wchar_t *v29; // [rsp+70h] [rbp+8h]

  v29 = a1;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  v12 = 0;
  while ( !v7 )
  {
    v14 = 3 * v12;
    v15 = qword_1400C7FA0[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp(a1, off_1400C7F90[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_1400C7FA0[v14]) - LODWORD(qword_1400C7FA0[v14]);
        if ( v10 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          goto LABEL_39;
        }
        if ( !v11 || !(_DWORD)v8 )
        {
          v21 = -1073741811;
          LODWORD(v28) = -1073741811;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1035, "ResolvedPath is NULL or zero size [%#x]", v28);
          return v21;
        }
        if ( v12 )
        {
          if ( !v9 )
          {
LABEL_20:
            v24 = RtlStringCchCopyW(v11, v8, (&off_1400C7F98)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[LODWORD(qword_1400C7FA0[v14])]);
            v21 = v25;
            if ( v25 < 0 )
            {
              LODWORD(v28) = v25;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1097, "RtlStringCchCatW failed [%x]", v28);
              return v21;
            }
          }
        }
        else
        {
          v16 = a5;
          for ( i = 0; i < 8; ++i )
          {
            v18 = a6;
            if ( word_1400C7F10[8 * i] == v16 && word_1400C7F12[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_1400C7F18)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[LODWORD(qword_1400C7FA0[v14])]);
              v21 = v23;
              if ( v23 < 0 )
              {
                LODWORD(v28) = v23;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1063, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v18 = a6;
              v16 = a5;
              v9 = 1;
            }
          }
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              "AslpEnvResolveVars",
              1074,
              "Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4",
              v16,
              v18);
            v11 = a3;
            goto LABEL_20;
          }
          v11 = a3;
        }
        v7 = 1;
      }
      a1 = v29;
    }
    if ( (unsigned __int64)++v12 >= 4 )
    {
      if ( !v7 )
      {
        if ( a2 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          *a7 = a2;
          return v21;
        }
        v10 = a2;
        v26 = RtlStringCchCopyW(v11, v8, a1);
        v21 = v26;
        if ( v26 < 0 )
        {
          LODWORD(v28) = v26;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1129, "RtlStringCchCopyW failed [%x]", v28);
          return v21;
        }
      }
      break;
    }
  }
  v21 = 0;
LABEL_39:
  *a7 = v10;
  return v21;
}

```

## disassembly

```asm
0x140018184  mov     [rsp+arg_8], rbx
0x140018189  mov     [rsp+arg_10], r8
0x14001818e  mov     [rsp+arg_0], rcx
0x140018193  push    rbp
0x140018194  push    rsi
0x140018195  push    rdi
0x140018196  push    r12
0x140018198  push    r13
0x14001819a  push    r14
0x14001819c  push    r15
0x14001819e  sub     rsp, 30h
0x1400181a2  xor     ebx, ebx
0x1400181a4  mov     r14d, r9d
0x1400181a7  xor     r13d, r13d
0x1400181aa  lea     r11, __ImageBase
0x1400181b1  xor     esi, esi
0x1400181b3  mov     rdi, r8
0x1400181b6  xor     r12d, r12d
0x1400181b9  mov     ebp, edx
0x1400181bb  test    ebx, ebx
0x1400181bd  jnz     loc_1400184A2
0x1400181c3  lea     r15, [r12+r12*2]
0x1400181c7  shl     r15, 3
0x1400181cb  mov     eax, [r15+r11+0C7FA0h]
0x1400181d3  cmp     ebp, eax
0x1400181d5  jbe     loc_1400183CB
0x1400181db  mov     rdx, [r15+r11+0C7F90h]; String2
0x1400181e3  mov     r8d, eax; MaxCount
0x1400181e6  call    _wcsnicmp
0x1400181eb  lea     r11, __ImageBase
0x1400181f2  test    eax, eax
0x1400181f4  jnz     loc_1400183C6
0x1400181fa  mov     esi, [r15+r11+0C7FA4h]
0x140018202  sub     esi, [r15+r11+0C7FA0h]
0x14001820a  add     esi, ebp
0x14001820c  cmp     esi, r14d
0x14001820f  ja      loc_140018472
0x140018215  test    rdi, rdi
0x140018218  jz      loc_140018449
0x14001821e  test    r14d, r14d
0x140018221  jz      loc_140018449
0x140018227  test    r12, r12
0x14001822a  jnz     loc_14001834A
0x140018230  movzx   ecx, [rsp+68h+arg_20]
0x140018238  lea     rdx, __ImageBase
0x14001823f  xor     edi, edi
0x140018241  movzx   eax, [rsp+68h+arg_28]
0x140018249  mov     r11, rdi
0x14001824c  add     r11, r11
0x14001824f  cmp     rva word_1400C7F10[rdx+r11*8], cx
0x140018258  jnz     loc_1400182FF
0x14001825e  cmp     rva word_1400C7F12[rdx+r11*8], ax
0x140018267  jnz     loc_1400182FF
0x14001826d  mov     r13, [rsp+68h+arg_10]
0x140018275  lea     r8, aSystemroot; "%systemroot%"
0x14001827c  mov     rcx, r13
0x14001827f  mov     rdx, r14
0x140018282  call    RtlStringCchCopyW
0x140018287  mov     ebx, eax
0x140018289  test    eax, eax
0x14001828b  js      loc_140018423
0x140018291  lea     r8, __ImageBase
0x140018298  mov     rdx, r14; unsigned __int64
0x14001829b  mov     r8, rva off_1400C7F18[r8+r11*8]; unsigned __int16 *
0x1400182a3  mov     rcx, r13; unsigned __int16 *
0x1400182a6  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400182ab  mov     ebx, eax
0x1400182ad  test    eax, eax
0x1400182af  js      loc_140018410
0x1400182b5  mov     rcx, [rsp+68h+arg_0]
0x1400182ba  lea     rax, __ImageBase
0x1400182c1  mov     eax, [r15+rax+0C7FA0h]
0x1400182c9  mov     rdx, r14; unsigned __int64
0x1400182cc  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x1400182d0  mov     rcx, r13; unsigned __int16 *
0x1400182d3  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400182d8  mov     ebx, eax
0x1400182da  test    eax, eax
0x1400182dc  js      loc_1400183FD
0x1400182e2  movzx   eax, [rsp+68h+arg_28]
0x1400182ea  lea     rdx, __ImageBase
0x1400182f1  movzx   ecx, [rsp+68h+arg_20]
0x1400182f9  mov     r13d, 1
0x1400182ff  inc     rdi
0x140018302  cmp     rdi, 8
0x140018306  jb      loc_140018241
0x14001830c  test    r13d, r13d
0x14001830f  jnz     loc_1400183B2
0x140018315  movzx   ecx, cx
0x140018318  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x14001831f  movzx   eax, ax
0x140018322  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140018329  mov     [rsp+68h+var_40], eax
0x14001832d  mov     r8d, 432h
0x140018333  mov     dword ptr [rsp+68h+var_48], ecx
0x140018337  lea     ecx, [r13+1]
0x14001833b  call    AslLogCallPrintf
0x140018340  mov     rdi, [rsp+68h+arg_10]
0x140018348  jmp     short loc_14001834F
0x14001834a  test    r13d, r13d
0x14001834d  jnz     short loc_1400183C1
0x14001834f  lea     rax, __ImageBase
0x140018356  mov     rdx, r14
0x140018359  mov     r8, [r15+rax+0C7F98h]
0x140018361  mov     rcx, rdi
0x140018364  call    RtlStringCchCopyW
0x140018369  mov     ebx, eax
0x14001836b  test    eax, eax
0x14001836d  js      loc_140018436
0x140018373  mov     rcx, [rsp+68h+arg_0]
0x140018378  lea     rax, __ImageBase
0x14001837f  mov     eax, [r15+rax+0C7FA0h]
0x140018387  mov     rdx, r14; unsigned __int64
0x14001838a  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x14001838e  mov     rcx, rdi; unsigned __int16 *
0x140018391  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018396  mov     ebx, eax
0x140018398  test    eax, eax
0x14001839a  jns     short loc_1400183BA
0x14001839c  mov     dword ptr [rsp+68h+var_48], eax
0x1400183a0  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x1400183a7  mov     r8d, 449h
0x1400183ad  jmp     loc_14001845F
0x1400183b2  mov     rdi, [rsp+68h+arg_10]
0x1400183ba  lea     r11, __ImageBase
0x1400183c1  mov     ebx, 1
0x1400183c6  mov     rcx, [rsp+68h+arg_0]
0x1400183cb  inc     r12
0x1400183ce  cmp     r12, 4
0x1400183d2  jb      loc_1400181BB
0x1400183d8  test    ebx, ebx
0x1400183da  jnz     loc_1400184A2
0x1400183e0  cmp     ebp, r14d
0x1400183e3  jbe     loc_140018479
0x1400183e9  mov     rax, [rsp+68h+arg_30]
0x1400183f1  mov     ebx, 0C0000023h
0x1400183f6  mov     [rax], ebp
0x1400183f8  jmp     loc_1400184AE
0x1400183fd  mov     dword ptr [rsp+68h+var_48], eax
0x140018401  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x140018408  mov     r8d, 427h
0x14001840e  jmp     short loc_14001845F
0x140018410  mov     dword ptr [rsp+68h+var_48], eax
0x140018414  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14001841b  mov     r8d, 421h
0x140018421  jmp     short loc_14001845F
0x140018423  mov     dword ptr [rsp+68h+var_48], eax
0x140018427  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14001842e  mov     r8d, 41Bh
0x140018434  jmp     short loc_14001845F
0x140018436  mov     dword ptr [rsp+68h+var_48], eax
0x14001843a  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x140018441  mov     r8d, 443h
0x140018447  jmp     short loc_14001845F
0x140018449  mov     ebx, 0C000000Dh
0x14001844e  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x140018455  mov     dword ptr [rsp+68h+var_48], ebx
0x140018459  mov     r8d, 40Bh
0x14001845f  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140018466  mov     ecx, 1
0x14001846b  call    AslLogCallPrintf
0x140018470  jmp     short loc_1400184AE
0x140018472  mov     ebx, 0C0000023h
0x140018477  jmp     short loc_1400184A4
0x140018479  mov     r8, rcx
0x14001847c  mov     rdx, r14
0x14001847f  mov     rcx, rdi
0x140018482  mov     esi, ebp
0x140018484  call    RtlStringCchCopyW
0x140018489  mov     ebx, eax
0x14001848b  test    eax, eax
0x14001848d  jns     short loc_1400184A2
0x14001848f  mov     dword ptr [rsp+68h+var_48], eax
0x140018493  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x14001849a  mov     r8d, 469h
0x1400184a0  jmp     short loc_14001845F
0x1400184a2  xor     ebx, ebx
0x1400184a4  mov     rax, [rsp+68h+arg_30]
0x1400184ac  mov     [rax], esi
0x1400184ae  mov     eax, ebx
0x1400184b0  mov     rbx, [rsp+68h+arg_8]
0x1400184b5  add     rsp, 30h
0x1400184b9  pop     r15
0x1400184bb  pop     r14
0x1400184bd  pop     r13
0x1400184bf  pop     r12
0x1400184c1  pop     rdi
0x1400184c2  pop     rsi
0x1400184c3  pop     rbp
0x1400184c4  retn
```
