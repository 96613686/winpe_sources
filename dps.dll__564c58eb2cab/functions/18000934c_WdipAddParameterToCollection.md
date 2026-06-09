# WdipAddParameterToCollection

- ea: `0x18000934c`
- end: `0x1800094b6`
- name: `WdipAddParameterToCollection`
- size: `362`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800094c0`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000934c`
- `0x18000a856`
- `0x180018b49`

## string_xrefs

- `0x180009460`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000949d`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipAddParameterToCollection(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  unsigned int v6; // edx
  size_t v7; // r14
  void *v8; // rax
  void *v9; // rsi
  unsigned __int64 v10; // rax
  unsigned int v11; // edx
  unsigned int v12; // eax
  int v13; // r8d

  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
        (int)L"WdipAddParameterToCollection",
        1231,
        (int)L"Error = %d",
        87);
      return v4;
    }
    v5 = *(unsigned int *)(a1 + 4);
    if ( (int)v5 + 1 >= (unsigned int)v5 )
    {
      v6 = 8 * v5 + 8;
      if ( (_DWORD)v5 + 1 == v6 >> 3 )
      {
        v7 = v6;
        v8 = (void *)WdipAlloc(v6);
        v9 = v8;
        if ( !v8 )
        {
          v4 = -2147024882;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
            (int)L"WdipAddParameterToCollection",
            1255,
            (int)L"Error = %d",
            14);
          return v4;
        }
        memset_0(v8, 0, v7);
        v10 = 8LL * *(unsigned int *)(a1 + 4);
        if ( v10 > 0xFFFFFFFF )
        {
          v13 = 1262;
        }
        else
        {
          memcpy_0(v9, *(const void **)(a1 + 8), (unsigned int)v10);
          *((_QWORD *)v9 + v5) = a2;
          WdipFree(*(_QWORD *)(a1 + 8));
          *(_QWORD *)(a1 + 8) = v9;
          v11 = *(_DWORD *)a1 + *(_DWORD *)(a2 + 32);
          if ( v11 >= *(_DWORD *)a1 )
          {
            v12 = *(_DWORD *)(a1 + 4);
            *(_DWORD *)a1 = v11;
            if ( v12 + 1 >= v12 )
            {
              *(_DWORD *)(a1 + 4) = v12 + 1;
              return 0;
            }
            *(_DWORD *)(a1 + 4) = -1;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
              (int)L"WdipAddParameterToCollection",
              1279,
              (int)L"Error = %d",
              22);
            return (unsigned int)-2147024362;
          }
          *(_DWORD *)a1 = -1;
          v13 = 1276;
        }
        v4 = -2147024362;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
          (int)L"WdipAddParameterToCollection",
          v13,
          (int)L"Error = %d",
          22);
        return v4;
      }
    }
    return (unsigned int)-2147024362;
  }
  v4 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
    (int)L"WdipAddParameterToCollection",
    1230,
    (int)L"Error = %d",
    87);
  return v4;
}

```

## disassembly

```asm
0x18000934c  push    rbx
0x18000934e  push    rbp
0x18000934f  push    rsi
0x180009350  push    rdi
0x180009351  push    r14
0x180009353  sub     rsp, 30h
0x180009357  mov     rbp, rdx
0x18000935a  mov     rbx, rcx
0x18000935d  test    rcx, rcx
0x180009360  jnz     short loc_18000937A
0x180009362  mov     ebx, 80070057h
0x180009367  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000936f  mov     r8d, 4CEh
0x180009375  jmp     loc_18000948F
0x18000937a  test    rbp, rbp
0x18000937d  jnz     short loc_180009397
0x18000937f  mov     ebx, 80070057h
0x180009384  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000938c  mov     r8d, 4CFh
0x180009392  jmp     loc_18000948F
0x180009397  mov     edi, [rcx+4]
0x18000939a  lea     ecx, [rdi+1]
0x18000939d  cmp     ecx, edi
0x18000939f  jnb     short loc_1800093AB
0x1800093a1  mov     ebx, 80070216h
0x1800093a6  jmp     loc_1800094A9
0x1800093ab  lea     edx, ds:8[rdi*8]
0x1800093b2  mov     eax, edx
0x1800093b4  shr     eax, 3
0x1800093b7  cmp     ecx, eax
0x1800093b9  jnz     short loc_1800093A1
0x1800093bb  mov     ecx, edx
0x1800093bd  mov     r14d, edx
0x1800093c0  call    WdipAlloc
0x1800093c5  mov     rsi, rax
0x1800093c8  test    rax, rax
0x1800093cb  jnz     short loc_1800093E5
0x1800093cd  mov     ebx, 8007000Eh
0x1800093d2  mov     dword ptr [rsp+58h+Args], 0Eh
0x1800093da  mov     r8d, 4E7h
0x1800093e0  jmp     loc_18000948F
0x1800093e5  mov     r8, r14; Size
0x1800093e8  xor     edx, edx; Val
0x1800093ea  mov     rcx, rsi; void *
0x1800093ed  call    memset_0
0x1800093f2  mov     eax, [rbx+4]
0x1800093f5  mov     r14d, 0FFFFFFFFh
0x1800093fb  shl     rax, 3
0x1800093ff  cmp     rax, r14
0x180009402  ja      short loc_18000947C
0x180009404  mov     rdx, [rbx+8]; Src
0x180009408  mov     rcx, rsi; void *
0x18000940b  mov     r8d, eax; Size
0x18000940e  call    memcpy_0
0x180009413  mov     [rsi+rdi*8], rbp
0x180009417  mov     rcx, [rbx+8]
0x18000941b  call    WdipFree
0x180009420  mov     [rbx+8], rsi
0x180009424  mov     edx, [rbp+20h]
0x180009427  add     edx, [rbx]
0x180009429  cmp     edx, [rbx]
0x18000942b  jb      short loc_180009471
0x18000942d  mov     eax, [rbx+4]
0x180009430  mov     [rbx], edx
0x180009432  lea     ecx, [rax+1]
0x180009435  cmp     ecx, eax
0x180009437  jb      short loc_180009440
0x180009439  mov     [rbx+4], ecx
0x18000943c  xor     ebx, ebx
0x18000943e  jmp     short loc_1800094A9
0x180009440  lea     r9, aErrorD; "Error = %d"
0x180009447  mov     [rbx+4], r14d
0x18000944b  mov     r8d, 4FFh; int
0x180009451  mov     dword ptr [rsp+58h+Args], 216h; Args
0x180009459  lea     rdx, aWdipaddparamet; "WdipAddParameterToCollection"
0x180009460  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009467  call    WdipTraceError
0x18000946c  jmp     loc_1800093A1
0x180009471  mov     [rbx], r14d
0x180009474  mov     r8d, 4FCh
0x18000947a  jmp     short loc_180009482
0x18000947c  mov     r8d, 4EEh; int
0x180009482  mov     dword ptr [rsp+58h+Args], 216h; Args
0x18000948a  mov     ebx, 80070216h
0x18000948f  lea     r9, aErrorD; "Error = %d"
0x180009496  lea     rdx, aWdipaddparamet; "WdipAddParameterToCollection"
0x18000949d  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800094a4  call    WdipTraceError
0x1800094a9  mov     eax, ebx
0x1800094ab  add     rsp, 30h
0x1800094af  pop     r14
0x1800094b1  pop     rdi
0x1800094b2  pop     rsi
0x1800094b3  pop     rbp
0x1800094b4  pop     rbx
0x1800094b5  retn
```
