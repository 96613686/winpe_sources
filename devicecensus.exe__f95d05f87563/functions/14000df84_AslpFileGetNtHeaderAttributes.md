# AslpFileGetNtHeaderAttributes

- ea: `0x14000df84`
- end: `0x14000e0bc`
- name: `AslpFileGetNtHeaderAttributes`
- size: `312`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, _DWORD *, _DWORD *, _WORD *, _WORD *, _WORD *, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000d9f8`

## callees

- `0x140007074`
- `0x14000dc74`
- `0x14000df84`

## string_xrefs

- `0x14000dfc1`: `AslpFileGetImageNtHeader failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetNtHeaderAttributes(
        _DWORD *a1,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _WORD *a5,
        _WORD *a6,
        _WORD *a7,
        _WORD *a8,
        __int64 a9)
{
  int ImageNtHeader; // eax
  unsigned int v14; // ebx
  __int64 v15; // r8
  __int16 v16; // dx
  __int16 v17; // cx
  _QWORD v19[6]; // [rsp+38h] [rbp-30h] BYREF

  v19[0] = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(v19, a9);
  v14 = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v15 = v19[0];
    *a2 = (unsigned __int8)*(_WORD *)(v19[0] + 70LL) + ((unsigned __int8)*(_WORD *)(v19[0] + 68LL) << 16);
    *a3 = *(_DWORD *)(v15 + 8);
    v16 = *(_WORD *)(v15 + 24);
    *a7 = v16;
    *a5 = *(_WORD *)(v15 + 4);
    *a8 = *(_WORD *)(v15 + 22);
    if ( v16 == 267 || v16 == 523 )
    {
      *a1 = *(_DWORD *)(v15 + 88);
      *a4 = *(_DWORD *)(v15 + 80);
      v17 = *(_WORD *)(v15 + 92);
      v14 = 0;
    }
    else
    {
      *a1 = 0;
      *a4 = 0;
      v17 = 0;
      v14 = -1073741637;
    }
    *a6 = v17;
  }
  else
  {
    AslLogCallPrintf(1, "AslpFileGetNtHeaderAttributes", 3635, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
  }
  return v14;
}

```

## disassembly

```asm
0x14000df84  push    rbx
0x14000df86  push    rsi
0x14000df87  push    rdi
0x14000df88  push    r14
0x14000df8a  push    r15
0x14000df8c  sub     rsp, 40h
0x14000df90  mov     rdi, r9
0x14000df93  mov     r14, r8
0x14000df96  mov     r15, rdx
0x14000df99  mov     rsi, rcx
0x14000df9c  mov     [rsp+68h+var_30], 0
0x14000dfa5  mov     rdx, [rsp+68h+arg_40]
0x14000dfad  lea     rcx, [rsp+68h+var_30]
0x14000dfb2  call    AslpFileGetImageNtHeader
0x14000dfb7  mov     ebx, eax
0x14000dfb9  test    eax, eax
0x14000dfbb  jns     short loc_14000DFE4
0x14000dfbd  mov     [rsp+68h+var_48], eax
0x14000dfc1  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14000dfc8  mov     r8d, 0E33h
0x14000dfce  lea     rdx, aAslpfilegetnth; "AslpFileGetNtHeaderAttributes"
0x14000dfd5  mov     ecx, 1
0x14000dfda  call    AslLogCallPrintf
0x14000dfdf  jmp     loc_14000E0AE
0x14000dfe4  mov     r8, [rsp+68h+var_30]
0x14000dfe9  movzx   eax, word ptr [r8+44h]
0x14000dfee  movzx   edx, al
0x14000dff1  shl     edx, 10h
0x14000dff4  movzx   eax, word ptr [r8+46h]
0x14000dff9  movzx   ecx, al
0x14000dffc  add     edx, ecx
0x14000dffe  mov     [r15], edx
0x14000e001  mov     eax, [r8+8]
0x14000e005  mov     [r14], eax
0x14000e008  movzx   edx, word ptr [r8+18h]
0x14000e00d  mov     rax, [rsp+68h+arg_30]
0x14000e015  mov     [rax], dx
0x14000e018  movzx   ecx, word ptr [r8+4]
0x14000e01d  mov     rax, [rsp+68h+arg_20]
0x14000e025  mov     [rax], cx
0x14000e028  movzx   ecx, word ptr [r8+16h]
0x14000e02d  mov     rax, [rsp+68h+arg_38]
0x14000e035  mov     [rax], cx
0x14000e038  mov     eax, 10Bh
0x14000e03d  cmp     dx, ax
0x14000e040  jz      short loc_14000E061
0x14000e042  mov     eax, 20Bh
0x14000e047  cmp     dx, ax
0x14000e04a  jz      short loc_14000E061
0x14000e04c  mov     dword ptr [rsi], 0
0x14000e052  mov     dword ptr [rdi], 0
0x14000e058  xor     ecx, ecx
0x14000e05a  mov     ebx, 0C00000BBh
0x14000e05f  jmp     short loc_14000E074
0x14000e061  mov     eax, [r8+58h]
0x14000e065  mov     [rsi], eax
0x14000e067  mov     eax, [r8+50h]
0x14000e06b  mov     [rdi], eax
0x14000e06d  movzx   ecx, word ptr [r8+5Ch]
0x14000e072  xor     ebx, ebx
0x14000e074  mov     rax, [rsp+68h+arg_28]
0x14000e07c  mov     [rax], cx
0x14000e07f  mov     [rsp+68h+var_38], ebx
0x14000e083  jmp     short loc_14000E0AE
0x14000e085  mov     ebx, eax
0x14000e087  mov     [rsp+68h+var_38], eax
0x14000e08b  mov     [rsp+68h+var_48], eax
0x14000e08f  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000e096  mov     r8d, 0E8Ah
0x14000e09c  lea     rdx, aAslpfilegetnth; "AslpFileGetNtHeaderAttributes"
0x14000e0a3  mov     ecx, 1
0x14000e0a8  call    AslLogCallPrintf
0x14000e0ad  nop
0x14000e0ae  mov     eax, ebx
0x14000e0b0  add     rsp, 40h
0x14000e0b4  pop     r15
0x14000e0b6  pop     r14
0x14000e0b8  pop     rdi
0x14000e0b9  pop     rsi
0x14000e0ba  pop     rbx
0x14000e0bb  retn
0x140011836  push    rbp
0x140011838  sub     rsp, 30h
0x14001183c  mov     rbp, rdx
0x14001183f  mov     rax, [rcx]
0x140011842  xor     ecx, ecx
0x140011844  cmp     dword ptr [rax], 0C00000FDh
0x14001184a  setnz   cl
0x14001184d  mov     [rbp+34h], ecx
0x140011850  mov     eax, [rbp+34h]
0x140011853  add     rsp, 30h
0x140011857  pop     rbp
0x140011858  retn
```
