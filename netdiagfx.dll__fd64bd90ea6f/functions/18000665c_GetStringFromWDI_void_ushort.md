# GetStringFromWDI(void *,ushort * *)

- ea: `0x18000665c`
- end: `0x180006705`
- name: `?GetStringFromWDI@@YAJPEAXPEAPEAG@Z`
- size: `169`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006350`

## callees

- `0x18000665c`

## import_xrefs

- `wdi!WdiGetParameterData` at `0x1800066d2`
- `wdi!WdiGetParameterData` at `0x1800066d2`
- `wdi!WdiGetParameterDataLength` at `0x180006687`
- `wdi!WdiGetParameterDataLength` at `0x180006687`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066e1`

## pseudocode

```c
__int64 __fastcall GetStringFromWDI(void *a1, unsigned __int16 **a2)
{
  __int64 result; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  result = WdiGetParameterDataLength(a1, &v10);
  if ( (int)result >= 0 )
  {
    v5 = (unsigned __int16 *)CoTaskMemAlloc(v10 + 2);
    v6 = v5;
    if ( v5 )
    {
      v7 = v10;
      v8 = v10 + 2;
      if ( v10 != -2 )
      {
        do
        {
          *(_BYTE *)v5 = 0;
          v5 = (unsigned __int16 *)((char *)v5 + 1);
          --v8;
        }
        while ( v8 );
        v7 = v10;
      }
      result = WdiGetParameterData(a1, v6, v7);
      v9 = result;
      if ( (int)result >= 0 )
      {
        *a2 = v6;
      }
      else
      {
        CoTaskMemFree(v6);
        return v9;
      }
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
0x18000665c  mov     rax, rsp
0x18000665f  mov     [rax+10h], rbx
0x180006663  mov     [rax+18h], rsi
0x180006667  push    rdi
0x180006668  sub     rsp, 20h
0x18000666c  mov     dword ptr [rax+8], 0
0x180006673  mov     rsi, rdx
0x180006676  mov     rdi, rcx
0x180006679  test    rcx, rcx
0x18000667c  jz      short loc_1800066F0
0x18000667e  test    rdx, rdx
0x180006681  jz      short loc_1800066F0
0x180006683  lea     rdx, [rax+8]
0x180006687  call    cs:__imp_WdiGetParameterDataLength
0x18000668d  test    eax, eax
0x18000668f  js      short loc_1800066F5
0x180006691  mov     ecx, [rsp+28h+arg_0]
0x180006695  add     ecx, 2; cb
0x180006698  call    cs:__imp_CoTaskMemAlloc
0x18000669e  mov     rbx, rax
0x1800066a1  test    rax, rax
0x1800066a4  jnz     short loc_1800066AD
0x1800066a6  mov     eax, 8007000Eh
0x1800066ab  jmp     short loc_1800066F5
0x1800066ad  mov     r8d, [rsp+28h+arg_0]
0x1800066b2  lea     ecx, [r8+2]
0x1800066b6  test    rcx, rcx
0x1800066b9  jz      short loc_1800066CC
0x1800066bb  mov     byte ptr [rax], 0
0x1800066be  inc     rax
0x1800066c1  sub     rcx, 1
0x1800066c5  jnz     short loc_1800066BB
0x1800066c7  mov     r8d, [rsp+28h+arg_0]
0x1800066cc  mov     rdx, rbx
0x1800066cf  mov     rcx, rdi
0x1800066d2  call    cs:__imp_WdiGetParameterData
0x1800066d8  mov     edi, eax
0x1800066da  test    eax, eax
0x1800066dc  jns     short loc_1800066EB
0x1800066de  mov     rcx, rbx; pv
0x1800066e1  call    cs:__imp_CoTaskMemFree
0x1800066e7  mov     eax, edi
0x1800066e9  jmp     short loc_1800066F5
0x1800066eb  mov     [rsi], rbx
0x1800066ee  jmp     short loc_1800066F5
0x1800066f0  mov     eax, 80070057h
0x1800066f5  mov     rbx, [rsp+28h+arg_8]
0x1800066fa  mov     rsi, [rsp+28h+arg_10]
0x1800066ff  add     rsp, 20h
0x180006703  pop     rdi
0x180006704  retn
```
