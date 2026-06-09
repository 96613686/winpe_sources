# LoEapPropertiesRemote

- ea: `0x180019164`
- end: `0x180019322`
- name: `LoEapPropertiesRemote`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018a30`

## callees

- `0x180002506`
- `0x180019164`
- `0x180048048`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800192a9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800192a9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180019280`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180019280`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019311`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019311`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800191f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800191f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192d7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800191c3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800191c3`
- `USER32!SendMessageW` at `0x18001919d`
- `USER32!SendMessageW` at `0x18001919d`

## pseudocode

```c
void __fastcall LoEapPropertiesRemote(__int64 a1)
{
  unsigned int *v1; // rbx
  HWND v3; // rcx
  int v4; // edi
  int v5; // r14d
  int v6; // eax
  LRESULT ItemDataPtr; // rax
  HRESULT v8; // eax
  HGLOBAL v9; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF
  void *Src; // [rsp+90h] [rbp+40h] BYREF
  __int64 v13; // [rsp+98h] [rbp+48h] BYREF

  v1 = 0;
  v3 = *(HWND *)(a1 + 384);
  Src = 0;
  LODWORD(dwBytes) = 0;
  ppv = 0;
  v4 = 0;
  v13 = 0;
  v5 = 0;
  v6 = SendMessageW(v3, 0x147u, 0, 0);
  ItemDataPtr = ComboBox_GetItemDataPtr(*(HWND *)(a1 + 384), v6);
  if ( ItemDataPtr )
  {
    v1 = *(unsigned int **)(ItemDataPtr + 16);
    v8 = CoInitializeEx(0, 2u);
    if ( v8 < 0 )
    {
      if ( v8 != -2147417850 )
        goto LABEL_13;
    }
    else
    {
      v4 = 1;
    }
    if ( CoCreateInstance((const IID *const)(v1 + 23), 0, 0x15u, &riid, &ppv) >= 0 )
    {
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             *(_QWORD *)(*(_QWORD *)a1 + 48LL),
             *v1,
             &v13) >= 0 )
      {
        v5 = 1;
        if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD, int, _QWORD, unsigned int, void **, SIZE_T *))(*(_QWORD *)ppv + 48LL))(
               ppv,
               *v1,
               v13,
               *(_QWORD *)(a1 + 8),
               1,
               *((_QWORD *)v1 + 8),
               v1[18],
               &Src,
               &dwBytes) >= 0 )
        {
          GlobalFree(*((HGLOBAL *)v1 + 8));
          *((_QWORD *)v1 + 8) = 0;
          v1[18] = 0;
          if ( !Src )
          {
LABEL_16:
            (*(void (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 32LL))(ppv, *v1, v13);
            goto LABEL_17;
          }
          if ( (_DWORD)dwBytes )
          {
            v9 = GlobalAlloc(0x40u, (unsigned int)dwBytes);
            *((_QWORD *)v1 + 8) = v9;
            if ( v9 )
            {
              memcpy_0(v9, Src, (unsigned int)dwBytes);
              v1[18] = dwBytes;
            }
          }
        }
      }
    }
    else
    {
      ppv = 0;
    }
  }
LABEL_13:
  if ( Src )
    CoTaskMemFree(Src);
  if ( v5 )
    goto LABEL_16;
LABEL_17:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180019164  push    rbp
0x180019166  push    rbx
0x180019167  push    rsi
0x180019168  push    rdi
0x180019169  push    r14
0x18001916b  mov     rbp, rsp
0x18001916e  sub     rsp, 50h
0x180019172  xor     ebx, ebx
0x180019174  mov     rsi, rcx
0x180019177  mov     rcx, [rcx+180h]; hWnd
0x18001917e  xor     r9d, r9d; lParam
0x180019181  xor     r8d, r8d; wParam
0x180019184  mov     [rbp+Src], rbx
0x180019188  mov     edx, 147h; Msg
0x18001918d  mov     dword ptr [rbp+dwBytes], ebx
0x180019190  mov     [rbp+arg_8], rbx
0x180019194  xor     edi, edi
0x180019196  mov     [rbp+arg_18], rbx
0x18001919a  xor     r14d, r14d
0x18001919d  call    cs:__imp_SendMessageW
0x1800191a3  mov     rcx, [rsi+180h]
0x1800191aa  mov     edx, eax
0x1800191ac  call    ComboBox_GetItemDataPtr
0x1800191b1  test    rax, rax
0x1800191b4  jz      loc_1800192CE
0x1800191ba  mov     rbx, [rax+10h]
0x1800191be  lea     edx, [rdi+2]; dwCoInit
0x1800191c1  xor     ecx, ecx; pvReserved
0x1800191c3  call    cs:__imp_CoInitializeEx
0x1800191c9  test    eax, eax
0x1800191cb  js      short loc_1800191D3
0x1800191cd  lea     edi, [r14+1]
0x1800191d1  jmp     short loc_1800191DE
0x1800191d3  cmp     eax, 80010106h
0x1800191d8  jnz     loc_1800192CE
0x1800191de  xor     edx, edx; pUnkOuter
0x1800191e0  lea     rax, [rbp+arg_8]
0x1800191e4  lea     rcx, [rbx+5Ch]; rclsid
0x1800191e8  mov     [rsp+50h+ppv], rax; ppv
0x1800191ed  lea     r9, riid; riid
0x1800191f4  lea     r8d, [rdx+15h]; dwClsContext
0x1800191f8  call    cs:__imp_CoCreateInstance
0x1800191fe  test    eax, eax
0x180019200  jns     short loc_18001920B
0x180019202  mov     [rbp+arg_8], r14
0x180019206  jmp     loc_1800192CE
0x18001920b  mov     rcx, [rbp+arg_8]
0x18001920f  lea     r9, [rbp+arg_18]
0x180019213  mov     rdx, [rsi]
0x180019216  mov     r8d, [rbx]
0x180019219  mov     rax, [rcx]
0x18001921c  mov     rdx, [rdx+30h]
0x180019220  mov     rax, [rax+18h]
0x180019224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019229  test    eax, eax
0x18001922b  js      loc_1800192CE
0x180019231  mov     rcx, [rbp+arg_8]
0x180019235  lea     rdx, [rbp+dwBytes]
0x180019239  mov     r9, [rsi+8]
0x18001923d  mov     r14d, 1
0x180019243  mov     r8, [rbp+arg_18]
0x180019247  mov     [rsp+50h+var_10], rdx
0x18001924c  lea     rdx, [rbp+Src]
0x180019250  mov     rax, [rcx]
0x180019253  mov     [rsp+50h+var_18], rdx
0x180019258  mov     edx, [rbx+48h]
0x18001925b  mov     [rsp+50h+var_20], edx
0x18001925f  mov     rdx, [rbx+40h]
0x180019263  mov     rax, [rax+30h]
0x180019267  mov     [rsp+50h+var_28], rdx
0x18001926c  mov     edx, [rbx]
0x18001926e  mov     dword ptr [rsp+50h+ppv], r14d
0x180019273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019278  test    eax, eax
0x18001927a  js      short loc_1800192CE
0x18001927c  mov     rcx, [rbx+40h]; hMem
0x180019280  call    cs:__imp_GlobalFree
0x180019286  mov     qword ptr [rbx+40h], 0
0x18001928e  mov     dword ptr [rbx+48h], 0
0x180019295  cmp     [rbp+Src], 0
0x18001929a  jz      short loc_1800192E2
0x18001929c  mov     eax, dword ptr [rbp+dwBytes]
0x18001929f  test    eax, eax
0x1800192a1  jz      short loc_1800192CE
0x1800192a3  mov     edx, eax; dwBytes
0x1800192a5  lea     ecx, [r14+3Fh]; uFlags
0x1800192a9  call    cs:__imp_GlobalAlloc
0x1800192af  mov     [rbx+40h], rax
0x1800192b3  test    rax, rax
0x1800192b6  jz      short loc_1800192CE
0x1800192b8  mov     r8d, dword ptr [rbp+dwBytes]; Size
0x1800192bc  mov     rcx, rax; void *
0x1800192bf  mov     rdx, [rbp+Src]; Src
0x1800192c3  call    memcpy_0
0x1800192c8  mov     eax, dword ptr [rbp+dwBytes]
0x1800192cb  mov     [rbx+48h], eax
0x1800192ce  mov     rcx, [rbp+Src]; pv
0x1800192d2  test    rcx, rcx
0x1800192d5  jz      short loc_1800192DD
0x1800192d7  call    cs:__imp_CoTaskMemFree
0x1800192dd  test    r14d, r14d
0x1800192e0  jz      short loc_1800192F8
0x1800192e2  mov     rcx, [rbp+arg_8]
0x1800192e6  mov     r8, [rbp+arg_18]
0x1800192ea  mov     edx, [rbx]
0x1800192ec  mov     rax, [rcx]
0x1800192ef  mov     rax, [rax+20h]
0x1800192f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f8  mov     rcx, [rbp+arg_8]
0x1800192fc  test    rcx, rcx
0x1800192ff  jz      short loc_18001930D
0x180019301  mov     rax, [rcx]
0x180019304  mov     rax, [rax+10h]
0x180019308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001930d  test    edi, edi
0x18001930f  jz      short loc_180019317
0x180019311  call    cs:__imp_CoUninitialize
0x180019317  add     rsp, 50h
0x18001931b  pop     r14
0x18001931d  pop     rdi
0x18001931e  pop     rsi
0x18001931f  pop     rbx
0x180019320  pop     rbp
0x180019321  retn
```
