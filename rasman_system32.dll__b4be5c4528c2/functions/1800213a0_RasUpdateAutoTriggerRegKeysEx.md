# RasUpdateAutoTriggerRegKeysEx

- ea: `0x1800213a0`
- end: `0x180021529`
- name: `RasUpdateAutoTriggerRegKeysEx`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800030d0`
- `0x1800213a0`
- `0x180021b14`
- `0x180021d84`

## pseudocode

```c
__int64 __fastcall RasUpdateAutoTriggerRegKeysEx(
        __int64 a1,
        const char *a2,
        __int64 a3,
        int a4,
        int a5,
        const char *a6,
        int a7,
        int a8)
{
  __int64 v9; // rax
  const char *v12; // r11
  const char *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  PVOID *v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-88h]
  __int64 v19; // [rsp+28h] [rbp-80h]
  __int64 v20; // [rsp+38h] [rbp-70h]
  __int64 v21; // [rsp+40h] [rbp-68h]

  v9 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v12 = a6;
    v13 = a2;
    if ( !a6 )
      v12 = L"<NULL>";
    if ( !a2 )
      v13 = L"<NULL>";
    WPP_SF_SScccSc(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v13, a4 != 0, a5 != 0, a8 != 0, (__int64)v12, a7 != 0);
    v9 = a3;
  }
  LODWORD(v21) = a8;
  LODWORD(v20) = a7;
  LODWORD(v19) = a5;
  LODWORD(v18) = a4;
  v14 = SubmitLocalRequest(0x9Bu, a1, a2, v9, v18, v19, a6, v20, v21);
  v15 = v14;
  if ( !v14 )
    goto LABEL_14;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 710, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
LABEL_14:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x40) != 0 && *((_BYTE *)v16 + 25) >= 6u )
    WPP_SF_d(v16[2], 711, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x1800213a0  mov     [rsp+arg_10], r8
0x1800213a5  push    rbx
0x1800213a6  push    rbp
0x1800213a7  push    rsi
0x1800213a8  push    rdi
0x1800213a9  push    r12
0x1800213ab  push    r13
0x1800213ad  push    r14
0x1800213af  push    r15
0x1800213b1  sub     rsp, 68h
0x1800213b5  mov     r14d, r9d
0x1800213b8  mov     rax, r8
0x1800213bb  mov     rdi, rdx
0x1800213be  mov     rsi, rcx
0x1800213c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213c8  lea     rdx, WPP_GLOBAL_Control
0x1800213cf  mov     r15d, [rsp+0A8h+arg_38]
0x1800213d7  mov     r12d, [rsp+0A8h+arg_30]
0x1800213df  mov     rbp, [rsp+0A8h+arg_28]
0x1800213e7  mov     r13d, [rsp+0A8h+arg_20]
0x1800213ef  cmp     rcx, rdx
0x1800213f2  jz      short loc_180021473
0x1800213f4  test    byte ptr [rcx+1Ch], 40h
0x1800213f8  jz      short loc_180021473
0x1800213fa  cmp     byte ptr [rcx+19h], 6
0x1800213fe  jb      short loc_180021473
0x180021400  mov     rcx, [rcx+10h]; LoggerHandle
0x180021404  lea     r9, aNull_2; "<NULL>"
0x18002140b  test    r12d, r12d
0x18002140e  mov     [rsp+0A8h+var_58], r9
0x180021413  mov     r11, rbp
0x180021416  mov     rax, rdi
0x180021419  setnz   bl
0x18002141c  test    rbp, rbp
0x18002141f  mov     [rsp+0A8h+var_60], bl; char
0x180021423  cmovz   r11, r9
0x180021427  test    r15d, r15d
0x18002142a  mov     [rsp+0A8h+var_68], r11; __int64
0x18002142f  setnz   r10b
0x180021433  test    r13d, r13d
0x180021436  mov     [rsp+0A8h+var_70], r10b; char
0x18002143b  setnz   r8b
0x18002143f  test    r14d, r14d
0x180021442  mov     [rsp+0A8h+var_78], r8b; char
0x180021447  setnz   dl
0x18002144a  test    rdi, rdi
0x18002144d  mov     [rsp+0A8h+var_80], dl; char
0x180021451  cmovz   rax, r9
0x180021455  test    rsi, rsi
0x180021458  mov     r9, rsi
0x18002145b  mov     [rsp+0A8h+var_88], rax; __int64
0x180021460  cmovz   r9, [rsp+0A8h+var_58]
0x180021466  call    WPP_SF_SScccSc
0x18002146b  mov     rax, [rsp+0A8h+arg_10]
0x180021473  mov     dword ptr [rsp+0A8h+var_68], r15d
0x180021478  mov     ecx, 9Bh
0x18002147d  mov     dword ptr [rsp+0A8h+var_70], r12d
0x180021482  mov     r9, rax
0x180021485  mov     qword ptr [rsp+0A8h+var_78], rbp
0x18002148a  mov     r8, rdi
0x18002148d  mov     dword ptr [rsp+0A8h+var_80], r13d
0x180021492  mov     rdx, rsi
0x180021495  mov     dword ptr [rsp+0A8h+var_88], r14d
0x18002149a  call    SubmitLocalRequest
0x18002149f  mov     ebx, eax
0x1800214a1  test    eax, eax
0x1800214a3  jz      short loc_1800214DE
0x1800214a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214ac  lea     rdi, WPP_GLOBAL_Control
0x1800214b3  cmp     rcx, rdi
0x1800214b6  jz      short loc_180021515
0x1800214b8  test    byte ptr [rcx+1Ch], 40h
0x1800214bc  jz      short loc_1800214EC
0x1800214be  cmp     byte ptr [rcx+19h], 2
0x1800214c2  jb      short loc_1800214EC
0x1800214c4  mov     rcx, [rcx+10h]
0x1800214c8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800214cf  mov     edx, 2C6h
0x1800214d4  mov     r9d, eax
0x1800214d7  call    WPP_SF_d
0x1800214dc  jmp     short loc_1800214E5
0x1800214de  lea     rdi, WPP_GLOBAL_Control
0x1800214e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214ec  cmp     rcx, rdi
0x1800214ef  jz      short loc_180021515
0x1800214f1  test    byte ptr [rcx+1Ch], 40h
0x1800214f5  jz      short loc_180021515
0x1800214f7  cmp     byte ptr [rcx+19h], 6
0x1800214fb  jb      short loc_180021515
0x1800214fd  mov     rcx, [rcx+10h]
0x180021501  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021508  mov     edx, 2C7h
0x18002150d  mov     r9d, ebx
0x180021510  call    WPP_SF_d
0x180021515  mov     eax, ebx
0x180021517  add     rsp, 68h
0x18002151b  pop     r15
0x18002151d  pop     r14
0x18002151f  pop     r13
0x180021521  pop     r12
0x180021523  pop     rdi
0x180021524  pop     rsi
0x180021525  pop     rbp
0x180021526  pop     rbx
0x180021527  retn
```
