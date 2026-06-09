# CMsftDiscFormat2RawCD::CacheCurrentWriteParametersModePage(IDiscRecorder2Ex *)

- ea: `0x18002d8a8`
- end: `0x18002da64`
- name: `?CacheCurrentWriteParametersModePage@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2Ex@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CMsftDiscFormat2RawCD *__hidden this, struct IDiscRecorder2Ex *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002ea20`
- `0x18002f540`

## callees

- `0x1800140f4`
- `0x180016778`
- `0x1800236b4`
- `0x18002d8a8`
- `0x180049832`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002d9b3`
- `ole32!CoTaskMemFree` at `0x18002d9c0`
- `ole32!CoTaskMemFree` at `0x18002d9b3`
- `ole32!CoTaskMemFree` at `0x18002d9c0`
- `ole32!CoTaskMemAlloc` at `0x18002d9d8`
- `ole32!CoTaskMemAlloc` at `0x18002d9d8`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2RawCD::CacheCurrentWriteParametersModePage(
        CMsftDiscFormat2RawCD *this,
        struct IDiscRecorder2Ex *a2)
{
  unsigned int v3; // edi
  void *v5; // rax
  void *v6; // rbp
  int v7; // ebx
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  pv = 0;
  LODWORD(cb) = 0;
  if ( *((_WORD *)this + 80) || !a2 )
  {
LABEL_13:
    v3 = -2147467259;
    goto LABEL_14;
  }
  v3 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, SIZE_T *))a2->lpVtbl->GetModePage)(
         a2,
         5,
         0,
         &pv,
         &cb);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 47), 100, &WPP_465922b870433540ecd6931719c7292a_Traceguids, v3);
    }
    goto LABEL_14;
  }
  if ( (unsigned int)cb < 0x34 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 47), 101, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    }
    goto LABEL_13;
  }
  v5 = CoTaskMemAlloc((unsigned int)cb);
  v6 = v5;
  if ( v5 )
  {
    v7 = cb;
    memcpy_0(v5, pv, (unsigned int)cb);
    *((_QWORD *)this + 30) = pv;
    *((_DWORD *)this + 62) = cb;
    *((_QWORD *)this + 32) = v6;
    *((_DWORD *)this + 66) = v7;
    return v3;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 102, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
  }
  v3 = -2147024882;
LABEL_14:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(0);
  return v3;
}

```

## disassembly

```asm
0x18002d8a8  mov     r11, rsp
0x18002d8ab  mov     [r11+10h], rbx
0x18002d8af  push    rbp
0x18002d8b0  push    rsi
0x18002d8b1  push    rdi
0x18002d8b2  sub     rsp, 40h
0x18002d8b6  xor     ebx, ebx
0x18002d8b8  mov     r10, rdx
0x18002d8bb  mov     rsi, rcx
0x18002d8be  mov     [r11+18h], rbx
0x18002d8c2  mov     dword ptr [rsp+58h+cb], ebx
0x18002d8c6  cmp     [rcx+0A0h], bx
0x18002d8cd  jnz     loc_18002D9A9
0x18002d8d3  test    rdx, rdx
0x18002d8d6  jz      loc_18002D9A9
0x18002d8dc  mov     rax, [rdx]
0x18002d8df  lea     rcx, [r11+8]
0x18002d8e3  mov     [r11-38h], rcx
0x18002d8e7  lea     r9, [r11+18h]
0x18002d8eb  xor     r8d, r8d
0x18002d8ee  lea     edx, [rbx+5]
0x18002d8f1  mov     rcx, r10
0x18002d8f4  mov     rax, [rax+68h]
0x18002d8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8fd  mov     edi, eax
0x18002d8ff  test    eax, eax
0x18002d901  jns     short loc_18002D94B
0x18002d903  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d90a  lea     rax, WPP_GLOBAL_Control
0x18002d911  cmp     rcx, rax
0x18002d914  jz      loc_18002D9AE
0x18002d91a  test    byte ptr [rcx+184h], 4
0x18002d921  jz      loc_18002D9AE
0x18002d927  cmp     byte ptr [rcx+181h], 3
0x18002d92e  jb      short loc_18002D9AE
0x18002d930  mov     rcx, [rcx+178h]
0x18002d937  lea     edx, [rbx+64h]
0x18002d93a  mov     r9d, edi
0x18002d93d  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002d944  call    WPP_SF_d
0x18002d949  jmp     short loc_18002D9AE
0x18002d94b  mov     r8d, dword ptr [rsp+58h+cb]
0x18002d950  mov     r9d, 34h ; '4'
0x18002d956  cmp     r8d, r9d
0x18002d959  jnb     short loc_18002D9D5
0x18002d95b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d962  lea     rax, WPP_GLOBAL_Control
0x18002d969  cmp     rcx, rax
0x18002d96c  jz      short loc_18002D9A9
0x18002d96e  test    byte ptr [rcx+184h], 4
0x18002d975  jz      short loc_18002D9A9
0x18002d977  cmp     byte ptr [rcx+181h], 3
0x18002d97e  jb      short loc_18002D9A9
0x18002d980  mov     rcx, [rcx+178h]
0x18002d987  lea     edx, [r9+31h]
0x18002d98b  mov     [rsp+58h+var_28], r9d
0x18002d990  mov     [rsp+58h+var_30], r9d
0x18002d995  mov     r9d, r8d
0x18002d998  mov     [rsp+58h+var_38], r8d
0x18002d99d  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002d9a4  call    WPP_SF_DDDd
0x18002d9a9  mov     edi, 80004005h
0x18002d9ae  mov     rcx, [rsp+58h+pv]; pv
0x18002d9b3  call    cs:__imp_CoTaskMemFree
0x18002d9b9  xor     ecx, ecx; pv
0x18002d9bb  mov     [rsp+58h+pv], rbx
0x18002d9c0  call    cs:__imp_CoTaskMemFree
0x18002d9c6  mov     rbx, [rsp+58h+arg_8]
0x18002d9cb  mov     eax, edi
0x18002d9cd  add     rsp, 40h
0x18002d9d1  pop     rdi
0x18002d9d2  pop     rsi
0x18002d9d3  pop     rbp
0x18002d9d4  retn
0x18002d9d5  mov     rcx, r8; cb
0x18002d9d8  call    cs:__imp_CoTaskMemAlloc
0x18002d9de  mov     rbp, rax
0x18002d9e1  test    rax, rax
0x18002d9e4  jnz     short loc_18002DA28
0x18002d9e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9ed  lea     rax, WPP_GLOBAL_Control
0x18002d9f4  cmp     rcx, rax
0x18002d9f7  jz      short loc_18002DA21
0x18002d9f9  test    byte ptr [rcx+184h], 4
0x18002da00  jz      short loc_18002DA21
0x18002da02  cmp     byte ptr [rcx+181h], 3
0x18002da09  jb      short loc_18002DA21
0x18002da0b  mov     rcx, [rcx+178h]
0x18002da12  lea     edx, [rbp+66h]
0x18002da15  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002da1c  call    WPP_SF_
0x18002da21  mov     edi, 8007000Eh
0x18002da26  jmp     short loc_18002D9AE
0x18002da28  mov     ebx, dword ptr [rsp+58h+cb]
0x18002da2c  mov     rcx, rbp; void *
0x18002da2f  mov     rdx, [rsp+58h+pv]; Src
0x18002da34  mov     r8d, ebx; Size
0x18002da37  call    memcpy_0
0x18002da3c  mov     rax, [rsp+58h+pv]
0x18002da41  mov     [rsi+0F0h], rax
0x18002da48  mov     eax, dword ptr [rsp+58h+cb]
0x18002da4c  mov     [rsi+0F8h], eax
0x18002da52  mov     [rsi+100h], rbp
0x18002da59  mov     [rsi+108h], ebx
0x18002da5f  jmp     loc_18002D9C6
```
