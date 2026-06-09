# DeviceSetStream(_MCIGRAPHIC *,uint,_GUID const *)

- ea: `0x18000310c`
- end: `0x180003207`
- name: `?DeviceSetStream@@YAJPEAU_MCIGRAPHIC@@IPEBU_GUID@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *, unsigned int, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005634`
- `0x180005804`

## callees

- `0x18000310c`
- `0x180006494`
- `0x180007010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800031e0`
- `ole32!CoTaskMemFree` at `0x1800031e0`

## pseudocode

```c
__int64 __fastcall DeviceSetStream(struct _MCIGRAPHIC *a1, int a2, const struct _GUID *a3)
{
  unsigned int i; // edi
  struct _AMMediaType *v7; // rbx
  LPVOID pv; // [rsp+88h] [rbp+20h] BYREF

  if ( *((_QWORD *)a1 + 24) )
  {
    pv = 0;
    for ( i = 0;
          !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, LPVOID *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 24) + 32LL))(
             *((_QWORD *)a1 + 24),
             i,
             &pv,
             0,
             0,
             0,
             0,
             0,
             0);
          ++i )
    {
      v7 = (struct _AMMediaType *)pv;
      if ( *(_QWORD *)pv == *(_QWORD *)&a3->Data1 && *((_QWORD *)pv + 1) == *(_QWORD *)a3->Data4 && !--a2 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)a1 + 24) + 40LL))(*((_QWORD *)a1 + 24), i, 1);
        v7 = (struct _AMMediaType *)pv;
      }
      if ( v7 )
      {
        FreeMediaType(v7);
        CoTaskMemFree(v7);
      }
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000310c  mov     rax, rsp
0x18000310f  mov     [rax+10h], rbx
0x180003113  mov     [rax+18h], rbp
0x180003117  push    rsi
0x180003118  push    rdi
0x180003119  push    r14
0x18000311b  sub     rsp, 50h
0x18000311f  cmp     qword ptr [rcx+0C0h], 0
0x180003127  mov     r14, r8
0x18000312a  mov     esi, edx
0x18000312c  mov     rbp, rcx
0x18000312f  jz      loc_1800031ED
0x180003135  mov     qword ptr [rax+20h], 0
0x18000313d  xor     edi, edi
0x18000313f  mov     rcx, [rbp+0C0h]
0x180003146  lea     r8, [rsp+68h+pv]
0x18000314e  mov     [rsp+68h+var_28], 0
0x180003157  xor     r9d, r9d
0x18000315a  mov     [rsp+68h+var_30], 0
0x180003163  mov     edx, edi
0x180003165  mov     [rsp+68h+var_38], 0
0x18000316e  mov     rax, [rcx]
0x180003171  mov     [rsp+68h+var_40], 0
0x18000317a  mov     [rsp+68h+var_48], 0
0x180003183  mov     rax, [rax+20h]
0x180003187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318c  test    eax, eax
0x18000318e  jnz     short loc_1800031ED
0x180003190  mov     rbx, [rsp+68h+pv]
0x180003198  mov     rax, [rbx]
0x18000319b  cmp     rax, [r14]
0x18000319e  jnz     short loc_1800031D0
0x1800031a0  mov     rax, [rbx+8]
0x1800031a4  cmp     rax, [r14+8]
0x1800031a8  jnz     short loc_1800031D0
0x1800031aa  add     esi, 0FFFFFFFFh
0x1800031ad  jnz     short loc_1800031D0
0x1800031af  mov     rcx, [rbp+0C0h]
0x1800031b6  lea     r8d, [rsi+1]
0x1800031ba  mov     edx, edi
0x1800031bc  mov     rax, [rcx]
0x1800031bf  mov     rax, [rax+28h]
0x1800031c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c8  mov     rbx, [rsp+68h+pv]
0x1800031d0  test    rbx, rbx
0x1800031d3  jz      short loc_1800031E6
0x1800031d5  mov     rcx, rbx; struct _AMMediaType *
0x1800031d8  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800031dd  mov     rcx, rbx; pv
0x1800031e0  call    cs:__imp_CoTaskMemFree
0x1800031e6  inc     edi
0x1800031e8  jmp     loc_18000313F
0x1800031ed  lea     r11, [rsp+68h+var_18]
0x1800031f2  mov     eax, 80004005h
0x1800031f7  mov     rbx, [r11+28h]
0x1800031fb  mov     rbp, [r11+30h]
0x1800031ff  mov     rsp, r11
0x180003202  pop     r14
0x180003204  pop     rdi
0x180003205  pop     rsi
0x180003206  retn
```
