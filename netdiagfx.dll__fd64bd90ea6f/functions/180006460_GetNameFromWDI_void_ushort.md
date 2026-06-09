# GetNameFromWDI(void *,ushort * *)

- ea: `0x180006460`
- end: `0x180006508`
- name: `?GetNameFromWDI@@YAJPEAXPEAPEAG@Z`
- size: `168`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800061c0`
- `0x180006350`

## callees

- `0x180006460`

## import_xrefs

- `wdi!WdiGetParameterName` at `0x18000648d`
- `wdi!WdiGetParameterName` at `0x1800064d5`
- `wdi!WdiGetParameterName` at `0x18000648d`
- `wdi!WdiGetParameterName` at `0x1800064d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800064a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800064a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064e4`

## pseudocode

```c
__int64 __fastcall GetNameFromWDI(void *a1, unsigned __int16 **a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rbx
  __int64 v7; // rcx
  int ParameterName; // esi
  int v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  result = WdiGetParameterName(a1, 0, &v9);
  if ( (int)result >= 0 )
  {
    v5 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v9 + 1));
    v6 = v5;
    if ( v5 )
    {
      v7 = (unsigned int)(v9 + 1);
      if ( v9 != -1 )
      {
        do
        {
          *(_BYTE *)v5 = 0;
          v5 = (unsigned __int16 *)((char *)v5 + 1);
          --v7;
        }
        while ( v7 );
      }
      ParameterName = WdiGetParameterName(a1, v6, &v9);
      if ( ParameterName >= 0 )
        *a2 = v6;
      else
        CoTaskMemFree(v6);
      return (unsigned int)ParameterName;
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
0x180006460  mov     rax, rsp
0x180006463  mov     [rax+10h], rbx
0x180006467  mov     [rax+18h], rsi
0x18000646b  push    rdi
0x18000646c  sub     rsp, 20h
0x180006470  mov     dword ptr [rax+8], 0
0x180006477  mov     rdi, rdx
0x18000647a  mov     rsi, rcx
0x18000647d  test    rcx, rcx
0x180006480  jz      short loc_1800064F3
0x180006482  test    rdx, rdx
0x180006485  jz      short loc_1800064F3
0x180006487  lea     r8, [rax+8]
0x18000648b  xor     edx, edx
0x18000648d  call    cs:__imp_WdiGetParameterName
0x180006493  test    eax, eax
0x180006495  js      short loc_1800064F8
0x180006497  mov     ecx, [rsp+28h+arg_0]
0x18000649b  inc     ecx
0x18000649d  add     rcx, rcx; cb
0x1800064a0  call    cs:__imp_CoTaskMemAlloc
0x1800064a6  mov     rbx, rax
0x1800064a9  test    rax, rax
0x1800064ac  jnz     short loc_1800064B5
0x1800064ae  mov     eax, 8007000Eh
0x1800064b3  jmp     short loc_1800064F8
0x1800064b5  mov     ecx, [rsp+28h+arg_0]
0x1800064b9  add     ecx, 1
0x1800064bc  jz      short loc_1800064CA
0x1800064be  mov     byte ptr [rax], 0
0x1800064c1  inc     rax
0x1800064c4  sub     rcx, 1
0x1800064c8  jnz     short loc_1800064BE
0x1800064ca  lea     r8, [rsp+28h+arg_0]
0x1800064cf  mov     rdx, rbx
0x1800064d2  mov     rcx, rsi
0x1800064d5  call    cs:__imp_WdiGetParameterName
0x1800064db  mov     esi, eax
0x1800064dd  test    eax, eax
0x1800064df  jns     short loc_1800064EC
0x1800064e1  mov     rcx, rbx; pv
0x1800064e4  call    cs:__imp_CoTaskMemFree
0x1800064ea  jmp     short loc_1800064EF
0x1800064ec  mov     [rdi], rbx
0x1800064ef  mov     eax, esi
0x1800064f1  jmp     short loc_1800064F8
0x1800064f3  mov     eax, 80070057h
0x1800064f8  mov     rbx, [rsp+28h+arg_8]
0x1800064fd  mov     rsi, [rsp+28h+arg_10]
0x180006502  add     rsp, 20h
0x180006506  pop     rdi
0x180006507  retn
```
