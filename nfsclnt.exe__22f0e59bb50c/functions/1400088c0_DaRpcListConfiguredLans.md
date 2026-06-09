# DaRpcListConfiguredLans

- ea: `0x1400088c0`
- end: `0x140008b48`
- name: `DaRpcListConfiguredLans`
- size: `648`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x140002c00`
- `0x140003a48`
- `0x140004bd4`
- `0x140004dd8`
- `0x140004e24`
- `0x1400088c0`
- `0x140009e0c`
- `0x14000a2d8`
- `0x14000a364`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140008924`
- `KERNEL32!EnterCriticalSection` at `0x140008924`
- `KERNEL32!LeaveCriticalSection` at `0x140008a7c`
- `KERNEL32!LeaveCriticalSection` at `0x140008b0d`
- `KERNEL32!LeaveCriticalSection` at `0x140008a7c`
- `KERNEL32!LeaveCriticalSection` at `0x140008b0d`

## pseudocode

```c
__int64 __fastcall DaRpcListConfiguredLans(__int64 a1, unsigned int *a2, unsigned int a3, _QWORD *a4, unsigned int *a5)
{
  __int64 v5; // r14
  unsigned int v6; // ebx
  unsigned int *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rdi
  _QWORD *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int v16; // esi
  __int64 v17; // r12
  _QWORD *v18; // rbx
  _QWORD *v19; // rcx

  v5 = a3;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
  v9 = a5;
  *a5 = 0;
  GetLanListFromRegistry();
  EnterCriticalSection(&LanListCS);
  v12 = pLanHead;
  v13 = pLanHead;
  if ( pLanHead )
  {
    do
    {
      v10 = v13[1];
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v10 + 2 * v14) );
      v13 = (_QWORD *)v13[6];
      v6 += 2 * v14 + 2;
    }
    while ( v13 );
  }
  *v9 = v6;
  if ( v6 > (unsigned int)v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v6, v5);
    v15 = 234;
LABEL_32:
    LeaveCriticalSection(&LanListCS);
    *a2 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v15);
    return v15;
  }
  v16 = 0;
  v17 = (__int64)a4 + v5;
  v18 = a4;
  if ( v12 )
  {
    v19 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
        WPP_SF_qS(v19[2], v10, v11, (_DWORD)v18, v12[1]);
      a5 = (unsigned int *)v12[1];
      v17 = PackString(&a5, v18, &NameStrings, v17);
      if ( v18 < a4 || v18 > (_QWORD *)((char *)a4 + v5 - 16) )
        break;
      *v18 = v17 - (_QWORD)a4;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          &WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
          v17 - (_QWORD)a4);
        v19 = WPP_GLOBAL_Control;
      }
      v12 = (_QWORD *)v12[6];
      v18 += 2;
      ++v16;
      if ( !v12 )
        goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v11, v18, a4, v5);
    v15 = 59;
    goto LABEL_32;
  }
LABEL_24:
  LeaveCriticalSection(&LanListCS);
  *a2 = v16;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v16);
  return 0;
}

```

## disassembly

```asm
0x1400088c0  push    rbx
0x1400088c2  push    rbp
0x1400088c3  push    rsi
0x1400088c4  push    rdi
0x1400088c5  push    r12
0x1400088c7  push    r13
0x1400088c9  push    r14
0x1400088cb  push    r15
0x1400088cd  sub     rsp, 38h
0x1400088d1  xor     r15d, r15d
0x1400088d4  mov     r14d, r8d
0x1400088d7  mov     ebx, r15d
0x1400088da  mov     rbp, r9
0x1400088dd  mov     r13, rdx
0x1400088e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088e7  lea     r12, WPP_GLOBAL_Control
0x1400088ee  cmp     rcx, r12
0x1400088f1  jz      short loc_14000890D
0x1400088f3  test    byte ptr [rcx+1Ch], 1
0x1400088f7  jz      short loc_14000890D
0x1400088f9  mov     rcx, [rcx+10h]
0x1400088fd  lea     edx, [r15+55h]
0x140008901  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008908  call    WPP_SF_q
0x14000890d  mov     rsi, [rsp+78h+arg_20]
0x140008915  mov     [rsi], r15d
0x140008918  call    GetLanListFromRegistry
0x14000891d  lea     rcx, LanListCS; lpCriticalSection
0x140008924  call    cs:__imp_EnterCriticalSection
0x14000892a  mov     rdi, cs:pLanHead
0x140008931  mov     rax, rdi
0x140008934  test    rdi, rdi
0x140008937  jz      short loc_14000895A
0x140008939  mov     rdx, [rax+8]
0x14000893d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140008941  inc     rcx
0x140008944  cmp     [rdx+rcx*2], r15w
0x140008949  jnz     short loc_140008941
0x14000894b  mov     rax, [rax+30h]
0x14000894f  lea     ebx, [rbx+rcx*2]
0x140008952  add     ebx, 2
0x140008955  test    rax, rax
0x140008958  jnz     short loc_140008939
0x14000895a  mov     [rsi], ebx
0x14000895c  cmp     ebx, r14d
0x14000895f  jbe     short loc_14000899A
0x140008961  mov     rcx, cs:WPP_GLOBAL_Control
0x140008968  cmp     rcx, r12
0x14000896b  jz      short loc_140008990
0x14000896d  test    byte ptr [rcx+1Ch], 2
0x140008971  jz      short loc_140008990
0x140008973  mov     rcx, [rcx+10h]
0x140008977  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000897e  mov     edx, 56h ; 'V'
0x140008983  mov     dword ptr [rsp+78h+var_58], r14d
0x140008988  mov     r9d, ebx
0x14000898b  call    WPP_SF_dd
0x140008990  mov     ebx, 0EAh
0x140008995  jmp     loc_140008B06
0x14000899a  mov     esi, r15d
0x14000899d  lea     r15, [r14+rbp]
0x1400089a1  mov     r12, r15
0x1400089a4  mov     rbx, rbp
0x1400089a7  test    rdi, rdi
0x1400089aa  jz      loc_140008A75
0x1400089b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089b7  lea     rax, WPP_GLOBAL_Control
0x1400089be  cmp     rcx, rax
0x1400089c1  jz      short loc_1400089DE
0x1400089c3  test    byte ptr [rcx+1Ch], 8
0x1400089c7  jz      short loc_1400089DE
0x1400089c9  mov     rax, [rdi+8]
0x1400089cd  mov     r9, rbx
0x1400089d0  mov     rcx, [rcx+10h]
0x1400089d4  mov     [rsp+78h+var_58], rax
0x1400089d9  call    WPP_SF_qS
0x1400089de  mov     rax, [rdi+8]
0x1400089e2  lea     r8, NameStrings
0x1400089e9  mov     r9, r12
0x1400089ec  mov     [rsp+78h+arg_20], rax
0x1400089f4  mov     rdx, rbx
0x1400089f7  lea     rcx, [rsp+78h+arg_20]
0x1400089ff  call    PackString
0x140008a04  mov     r12, rax
0x140008a07  cmp     rbx, rbp
0x140008a0a  jb      loc_140008ACA
0x140008a10  lea     rax, [r15-10h]
0x140008a14  cmp     rbx, rax
0x140008a17  ja      loc_140008ACA
0x140008a1d  mov     r9, r12
0x140008a20  sub     r9, rbp
0x140008a23  mov     [rbx], r9
0x140008a26  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a2d  lea     rax, WPP_GLOBAL_Control
0x140008a34  cmp     rcx, rax
0x140008a37  jz      short loc_140008A62
0x140008a39  test    byte ptr [rcx+1Ch], 8
0x140008a3d  jz      short loc_140008A62
0x140008a3f  mov     rcx, [rcx+10h]
0x140008a43  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008a4a  mov     edx, 59h ; 'Y'
0x140008a4f  call    WPP_SF_S
0x140008a54  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a5b  lea     rax, WPP_GLOBAL_Control
0x140008a62  mov     rdi, [rdi+30h]
0x140008a66  add     rbx, 10h
0x140008a6a  inc     esi
0x140008a6c  test    rdi, rdi
0x140008a6f  jnz     loc_1400089BE
0x140008a75  lea     rcx, LanListCS; lpCriticalSection
0x140008a7c  call    cs:__imp_LeaveCriticalSection
0x140008a82  mov     [r13+0], esi
0x140008a86  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a8d  lea     rax, WPP_GLOBAL_Control
0x140008a94  cmp     rcx, rax
0x140008a97  jz      short loc_140008AB7
0x140008a99  test    byte ptr [rcx+1Ch], 1
0x140008a9d  jz      short loc_140008AB7
0x140008a9f  mov     rcx, [rcx+10h]
0x140008aa3  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008aaa  mov     edx, 5Ah ; 'Z'
0x140008aaf  mov     r9d, esi
0x140008ab2  call    WPP_SF_d
0x140008ab7  xor     eax, eax
0x140008ab9  add     rsp, 38h
0x140008abd  pop     r15
0x140008abf  pop     r14
0x140008ac1  pop     r13
0x140008ac3  pop     r12
0x140008ac5  pop     rdi
0x140008ac6  pop     rsi
0x140008ac7  pop     rbp
0x140008ac8  pop     rbx
0x140008ac9  retn
0x140008aca  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ad1  lea     r12, WPP_GLOBAL_Control
0x140008ad8  cmp     rcx, r12
0x140008adb  jz      short loc_140008AFE
0x140008add  test    byte ptr [rcx+1Ch], 2
0x140008ae1  jz      short loc_140008AFE
0x140008ae3  mov     rcx, [rcx+10h]
0x140008ae7  mov     edx, 58h ; 'X'
0x140008aec  mov     [rsp+78h+var_50], r14d
0x140008af1  mov     r9, rbx
0x140008af4  mov     [rsp+78h+var_58], rbp
0x140008af9  call    WPP_SF_qqD
0x140008afe  mov     ebx, 3Bh ; ';'
0x140008b03  xor     r15d, r15d
0x140008b06  lea     rcx, LanListCS; lpCriticalSection
0x140008b0d  call    cs:__imp_LeaveCriticalSection
0x140008b13  mov     [r13+0], r15d
0x140008b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b1e  cmp     rcx, r12
0x140008b21  jz      short loc_140008B41
0x140008b23  test    byte ptr [rcx+1Ch], 2
0x140008b27  jz      short loc_140008B41
0x140008b29  mov     rcx, [rcx+10h]
0x140008b2d  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008b34  mov     edx, 5Bh ; '['
0x140008b39  mov     r9d, ebx
0x140008b3c  call    WPP_SF_d
0x140008b41  mov     eax, ebx
0x140008b43  jmp     loc_140008AB9
```
