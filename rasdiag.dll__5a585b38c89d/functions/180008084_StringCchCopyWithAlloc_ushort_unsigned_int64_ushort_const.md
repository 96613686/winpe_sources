# StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)

- ea: `0x180008084`
- end: `0x180008175`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z`
- size: `241`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006274`
- `0x1800068b0`
- `0x180006ac0`
- `0x180007dc0`
- `0x1800084a0`
- `0x1800086b0`
- `0x180009c90`
- `0x180009e60`
- `0x18000ac20`
- `0x18000ad60`
- `0x18000d100`

## callees

- `0x180008084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800080ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800080ee`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rsi
  __int64 v5; // rdi
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  unsigned int v8; // ebx
  __int64 result; // rax
  __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rdx

  v3 = a3;
  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v5 = a2 - 1;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFF )
    return 2147942487LL;
  v6 = a2 - 1;
  v7 = a3;
  v8 = -2147024809;
  if ( v5 )
  {
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
        goto LABEL_7;
    }
    result = 0;
    v10 = v5 - v6;
  }
  else
  {
LABEL_7:
    result = 2147942487LL;
    v10 = 0;
  }
  if ( (int)result >= 0 )
  {
    v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10 + 2);
    *a1 = v11;
    v12 = v11;
    if ( v11 )
    {
      v13 = v10 + 1;
      if ( v10 != -1 )
      {
        if ( v13 <= 0x7FFFFFFF )
        {
          v14 = 2147483646;
          v8 = 0;
          while ( v14 )
          {
            if ( *v3 )
            {
              *v12++ = *v3++;
              --v14;
              if ( --v13 )
                continue;
            }
            if ( !v13 )
            {
              --v12;
              v8 = -2147024774;
            }
            break;
          }
        }
        *v12 = 0;
      }
      return v8;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008084  push    rbx
0x180008086  push    rbp
0x180008087  push    rsi
0x180008088  push    rdi
0x180008089  push    r14
0x18000808b  sub     rsp, 20h
0x18000808f  xor     ebp, ebp
0x180008091  mov     rsi, r8
0x180008094  mov     r14, rcx
0x180008097  test    rcx, rcx
0x18000809a  jz      loc_180008164
0x1800080a0  test    r8, r8
0x1800080a3  jz      loc_180008164
0x1800080a9  lea     rdi, [rdx-1]
0x1800080ad  cmp     rdi, 7FFFFFFFh
0x1800080b4  ja      loc_180008164
0x1800080ba  mov     rdx, rdi
0x1800080bd  mov     rax, r8
0x1800080c0  mov     ebx, 80070057h
0x1800080c5  test    rdi, rdi
0x1800080c8  jz      short loc_1800080D9
0x1800080ca  cmp     [rax], bp
0x1800080cd  jz      short loc_18000810C
0x1800080cf  add     rax, 2
0x1800080d3  sub     rdx, 1
0x1800080d7  jnz     short loc_1800080CA
0x1800080d9  mov     eax, ebx
0x1800080db  mov     rdi, rbp
0x1800080de  test    eax, eax
0x1800080e0  js      loc_180008169
0x1800080e6  lea     rcx, ds:2[rdi*2]; cb
0x1800080ee  call    cs:__imp_CoTaskMemAlloc
0x1800080f5  nop     dword ptr [rax+rax+00h]
0x1800080fa  mov     [r14], rax
0x1800080fd  mov     rcx, rax
0x180008100  test    rax, rax
0x180008103  jnz     short loc_180008113
0x180008105  mov     eax, 8007000Eh
0x18000810a  jmp     short loc_180008169
0x18000810c  mov     eax, ebp
0x18000810e  sub     rdi, rdx
0x180008111  jmp     short loc_1800080DE
0x180008113  lea     rax, [rdi+1]
0x180008117  test    rax, rax
0x18000811a  jz      short loc_180008160
0x18000811c  cmp     rax, 7FFFFFFFh
0x180008122  ja      short loc_18000815D
0x180008124  mov     edx, 7FFFFFFEh
0x180008129  mov     ebx, ebp
0x18000812b  test    rdx, rdx
0x18000812e  jz      short loc_18000815D
0x180008130  movzx   r8d, word ptr [rsi]
0x180008134  test    r8w, r8w
0x180008138  jz      short loc_18000814F
0x18000813a  mov     [rcx], r8w
0x18000813e  add     rsi, 2
0x180008142  add     rcx, 2
0x180008146  dec     rdx
0x180008149  sub     rax, 1
0x18000814d  jnz     short loc_18000812B
0x18000814f  test    rax, rax
0x180008152  jnz     short loc_18000815D
0x180008154  sub     rcx, 2
0x180008158  mov     ebx, 8007007Ah
0x18000815d  mov     [rcx], bp
0x180008160  mov     eax, ebx
0x180008162  jmp     short loc_180008169
0x180008164  mov     eax, 80070057h
0x180008169  add     rsp, 20h
0x18000816d  pop     r14
0x18000816f  pop     rdi
0x180008170  pop     rsi
0x180008171  pop     rbp
0x180008172  pop     rbx
0x180008173  retn
```
