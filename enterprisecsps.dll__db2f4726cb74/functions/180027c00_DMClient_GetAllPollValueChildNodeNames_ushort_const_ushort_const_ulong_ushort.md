# DMClient::GetAllPollValueChildNodeNames(ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x180027c00`
- end: `0x180027d96`
- name: `?GetAllPollValueChildNodeNames@DMClient@@YAJPEBG0PEAKPEAPEAPEAG@Z`
- size: `406`
- prototype: `__int64 __fastcall(DMClient *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800362a0`

## callees

- `0x180027c00`
- `0x1800297ec`
- `0x18002a93c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180027d0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d41`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d41`
- `OLEAUT32!__imp_VariantInit` at `0x180027c39`
- `OLEAUT32!__imp_VariantInit` at `0x180027c39`
- `OLEAUT32!__imp_VariantClear` at `0x180027cf5`
- `OLEAUT32!__imp_VariantClear` at `0x180027d76`
- `OLEAUT32!__imp_VariantClear` at `0x180027cf5`
- `OLEAUT32!__imp_VariantClear` at `0x180027d76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027c6e`

## pseudocode

```c
__int64 __fastcall DMClient::GetAllPollValueChildNodeNames(
        DMClient *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  _QWORD *v8; // rdi
  int v9; // ebx
  __int64 v10; // rbp
  int i; // esi
  struct tagVARIANT *v12; // r9
  int PollValue; // eax
  BSTR v14; // rax
  __int64 j; // rsi
  OLECHAR *v16; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-68h] BYREF
  int v19; // [rsp+90h] [rbp+8h] BYREF

  v19 = 8;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( this && a3 && a4 && a2 )
  {
    v8 = CoTaskMemAlloc(0x30u);
    if ( v8 )
    {
      v10 = 0;
      v9 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= 6 )
        {
          *(_DWORD *)a3 = v10;
          *(_QWORD *)a4 = v8;
          goto LABEL_24;
        }
        v9 = DMClient::PollNameToRegistry((&c_rgPollValues)[i], &v19);
        if ( v9 < 0 )
          break;
        PollValue = DMClient::GetPollValue(this, (const unsigned __int16 *)(&c_rgPollValues)[i], &pvarg.vt, v12);
        v9 = PollValue;
        if ( PollValue == -2147024894 )
        {
          v19 = 8;
          v9 = 0;
        }
        else
        {
          if ( PollValue < 0 )
            break;
          VariantClear(&pvarg);
          v14 = SysAllocString((const OLECHAR *)(&c_rgPollValues)[i]);
          v8[v10] = v14;
          if ( !v14 )
          {
            v9 = -2147024882;
            break;
          }
          v10 = (unsigned int)(v10 + 1);
        }
      }
      for ( j = 0; (unsigned int)j < (unsigned int)v10; j = (unsigned int)(j + 1) )
      {
        v16 = (OLECHAR *)v8[j];
        if ( v16 )
          SysFreeString(v16);
      }
      CoTaskMemFree(v8);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_24:
  VariantClear(&pvarg);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027c00  mov     r11, rsp
0x180027c03  push    rbx
0x180027c04  push    rbp
0x180027c05  push    rsi
0x180027c06  push    rdi
0x180027c07  push    r12
0x180027c09  push    r13
0x180027c0b  push    r14
0x180027c0d  push    r15
0x180027c0f  sub     rsp, 48h
0x180027c13  xorps   xmm0, xmm0
0x180027c16  mov     dword ptr [r11+8], 8
0x180027c1e  mov     r13, rcx
0x180027c21  xor     eax, eax
0x180027c23  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180027c28  lea     rcx, [r11-68h]; pvarg
0x180027c2c  mov     [r11-58h], rax
0x180027c30  mov     r14, r9
0x180027c33  mov     r15, r8
0x180027c36  mov     rbx, rdx
0x180027c39  call    cs:__imp_VariantInit
0x180027c40  nop     dword ptr [rax+rax+00h]
0x180027c45  test    r13, r13
0x180027c48  jz      loc_180027D6C
0x180027c4e  test    r15, r15
0x180027c51  jz      loc_180027D6C
0x180027c57  test    r14, r14
0x180027c5a  jz      loc_180027D6C
0x180027c60  test    rbx, rbx
0x180027c63  jz      loc_180027D6C
0x180027c69  mov     ecx, 30h ; '0'; cb
0x180027c6e  call    cs:__imp_CoTaskMemAlloc
0x180027c75  nop     dword ptr [rax+rax+00h]
0x180027c7a  mov     rdi, rax
0x180027c7d  test    rax, rax
0x180027c80  jnz     short loc_180027C8C
0x180027c82  mov     ebx, 8007000Eh
0x180027c87  jmp     loc_180027D71
0x180027c8c  xor     ebp, ebp
0x180027c8e  xor     ebx, ebx
0x180027c90  xor     esi, esi
0x180027c92  cmp     esi, 6
0x180027c95  jge     loc_180027D64
0x180027c9b  lea     rax, ?c_rgPollValues@@3PAPEBGA; ushort const * near * c_rgPollValues
0x180027ca2  movsxd  r12, esi
0x180027ca5  lea     rdx, [rsp+88h+arg_0]
0x180027cad  mov     rcx, [rax+r12*8]
0x180027cb1  call    DMClient__PollNameToRegistry
0x180027cb6  mov     ebx, eax
0x180027cb8  test    eax, eax
0x180027cba  js      short loc_180027D2F
0x180027cbc  lea     rdx, ?c_rgPollValues@@3PAPEBGA; ushort const * near * c_rgPollValues
0x180027cc3  mov     rcx, r13; this
0x180027cc6  mov     rdx, [rdx+r12*8]; unsigned __int16 *
0x180027cca  lea     r8, [rsp+88h+pvarg]; unsigned __int16 *
0x180027ccf  call    ?GetPollValue@DMClient@@YAJPEBG0PEAUtagVARIANT@@@Z; DMClient::GetPollValue(ushort const *,ushort const *,tagVARIANT *)
0x180027cd4  mov     ebx, eax
0x180027cd6  cmp     eax, 80070002h
0x180027cdb  jnz     short loc_180027CEC
0x180027cdd  mov     [rsp+88h+arg_0], 8
0x180027ce8  xor     ebx, ebx
0x180027cea  jmp     short loc_180027D23
0x180027cec  test    eax, eax
0x180027cee  js      short loc_180027D2F
0x180027cf0  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180027cf5  call    cs:__imp_VariantClear
0x180027cfc  nop     dword ptr [rax+rax+00h]
0x180027d01  lea     rax, ?c_rgPollValues@@3PAPEBGA; ushort const * near * c_rgPollValues
0x180027d08  mov     rcx, [rax+r12*8]; psz
0x180027d0c  call    cs:__imp_SysAllocString
0x180027d13  nop     dword ptr [rax+rax+00h]
0x180027d18  mov     [rdi+rbp*8], rax
0x180027d1c  test    rax, rax
0x180027d1f  jz      short loc_180027D2A
0x180027d21  inc     ebp
0x180027d23  inc     esi
0x180027d25  jmp     loc_180027C92
0x180027d2a  mov     ebx, 8007000Eh
0x180027d2f  xor     esi, esi
0x180027d31  mov     r14, rdi
0x180027d34  test    ebp, ebp
0x180027d36  jz      short loc_180027D53
0x180027d38  mov     rcx, [r14+rsi*8]; bstrString
0x180027d3c  test    rcx, rcx
0x180027d3f  jz      short loc_180027D4D
0x180027d41  call    cs:__imp_SysFreeString
0x180027d48  nop     dword ptr [rax+rax+00h]
0x180027d4d  inc     esi
0x180027d4f  cmp     esi, ebp
0x180027d51  jb      short loc_180027D38
0x180027d53  mov     rcx, rdi; pv
0x180027d56  call    cs:__imp_CoTaskMemFree
0x180027d5d  nop     dword ptr [rax+rax+00h]
0x180027d62  jmp     short loc_180027D71
0x180027d64  mov     [r15], ebp
0x180027d67  mov     [r14], rdi
0x180027d6a  jmp     short loc_180027D71
0x180027d6c  mov     ebx, 80070057h
0x180027d71  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180027d76  call    cs:__imp_VariantClear
0x180027d7d  nop     dword ptr [rax+rax+00h]
0x180027d82  mov     eax, ebx
0x180027d84  add     rsp, 48h
0x180027d88  pop     r15
0x180027d8a  pop     r14
0x180027d8c  pop     r13
0x180027d8e  pop     r12
0x180027d90  pop     rdi
0x180027d91  pop     rsi
0x180027d92  pop     rbp
0x180027d93  pop     rbx
0x180027d94  retn
```
