# DirectUI::Value::_ZeroRelease(void)

- ea: `0x18008638c`
- end: `0x1800865de`
- name: `?_ZeroRelease@Value@DirectUI@@AEAAXXZ`
- size: `594`
- prototype: `void __fastcall(DirectUI::Value *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180085548`

## callees

- `0x1800831b8`
- `0x18008344c`
- `0x18008638c`
- `0x18016586c`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008639e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008639e`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008644d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008644d`
- `GDI32!DeleteObject` at `0x180086520`
- `GDI32!DeleteObject` at `0x180086533`
- `GDI32!DeleteObject` at `0x180086520`
- `GDI32!DeleteObject` at `0x180086533`
- `GDI32!DeleteEnhMetaFile` at `0x1800864f7`
- `GDI32!DeleteEnhMetaFile` at `0x18008650a`
- `GDI32!DeleteEnhMetaFile` at `0x1800864f7`
- `GDI32!DeleteEnhMetaFile` at `0x18008650a`
- `USER32!DestroyIcon` at `0x1800864a0`
- `USER32!DestroyIcon` at `0x1800864b3`
- `USER32!DestroyIcon` at `0x1800864a0`
- `USER32!DestroyIcon` at `0x1800864b3`

## pseudocode

```c
void __fastcall DirectUI::Value::_ZeroRelease(DirectUI **this)
{
  _QWORD *Value; // rax
  void *v3; // rdx
  __int64 v4; // rsi
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  DirectUI *v15; // rcx
  ATOM v16; // cx
  DirectUI *v17; // rdx
  HICON v18; // rcx
  DirectUI *v19; // rcx
  HENHMETAFILE v20; // rcx
  void *v21; // rcx
  DirectUI *v22; // rcx
  DirectUI *v23; // rbx
  DirectUI *v24; // rcx

  Value = TlsGetValue(DirectUI::g_dwElSlot);
  if ( Value )
    v4 = Value[2];
  else
    v4 = 0;
  if ( (*(_DWORD *)this & 0x40) != 0 )
    goto LABEL_11;
  v5 = (int)(*(_DWORD *)this << 26) >> 26;
  if ( v5 > 12 )
  {
    v11 = v5 - 13;
    if ( !v11 )
      goto LABEL_21;
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 3;
      if ( !v13 )
      {
        DirectUI::SafeDestroyValueList(this[1]);
        goto LABEL_11;
      }
      v14 = v13 - 2;
      if ( v14 )
      {
        if ( v14 != 6 )
          goto LABEL_11;
        goto LABEL_21;
      }
      v23 = this[1];
      DirectUI::DynamicArrayBase<double,DirectUI::DoubleAllocationPolicy<double>,1,0>::Release(v23);
      goto LABEL_57;
    }
    v16 = *((_WORD *)this + 4);
    if ( v16 )
      DeleteAtom(v16);
  }
  else
  {
    if ( v5 != 12 )
    {
      v6 = v5 - 4;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 4;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              if ( v9 != 1 )
                goto LABEL_11;
              v17 = this[1];
              if ( (*((_BYTE *)v17 + 20) & 7) != 0 )
              {
                if ( (*((_BYTE *)v17 + 20) & 7) == 1 )
                  goto LABEL_34;
                if ( (*((_BYTE *)v17 + 20) & 7) == 2 )
                {
                  if ( *(_QWORD *)v17 && (*((_BYTE *)v17 + 21) & 4) == 0 )
                    DeleteEnhMetaFile(*(HENHMETAFILE *)v17);
                  v20 = (HENHMETAFILE)*((_QWORD *)this[1] + 1);
                  if ( v20 )
                    DeleteEnhMetaFile(v20);
                  goto LABEL_52;
                }
                if ( (*((_BYTE *)v17 + 20) & 7) != 4 )
                {
                  if ( (*((_BYTE *)v17 + 20) & 7) != 5 )
                  {
LABEL_52:
                    v22 = this[1];
                    if ( v22 )
                    {
                      DirectUI::AccHFree(v22, v17);
                      this[1] = 0;
                    }
                    goto LABEL_11;
                  }
LABEL_34:
                  if ( *(_QWORD *)v17 && (*((_BYTE *)v17 + 21) & 4) == 0 )
                    DestroyIcon(*(HICON *)v17);
                  v18 = (HICON)*((_QWORD *)this[1] + 1);
                  if ( v18 )
                    DestroyIcon(v18);
                  v19 = (DirectUI *)*((_QWORD *)this[1] + 5);
                  if ( (unsigned __int64)v19 >= 0x10000 )
                    DirectUI::AccHFree(v19, v17);
                  goto LABEL_52;
                }
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
                *(_QWORD *)this[1] = 0;
              }
              else if ( *(_QWORD *)v17 && (*((_BYTE *)v17 + 21) & 4) == 0 )
              {
                DeleteObject(*(HGDIOBJ *)v17);
              }
              v21 = (void *)*((_QWORD *)this[1] + 1);
              if ( v21 )
                DeleteObject(v21);
              goto LABEL_52;
            }
            v23 = this[1];
            if ( !v23 )
              goto LABEL_11;
            (*(void (__fastcall **)(DirectUI *, _QWORD))(*(_QWORD *)v23 + 64LL))(this[1], 0);
            goto LABEL_57;
          }
          if ( *((_BYTE *)this + 8) != 6 )
            goto LABEL_11;
          v15 = this[2];
LABEL_22:
          if ( !v15 )
            goto LABEL_11;
          goto LABEL_23;
        }
LABEL_21:
        v15 = this[1];
        goto LABEL_22;
      }
      v23 = this[1];
      if ( !v23 )
        goto LABEL_11;
      DirectUI::DynamicArrayBase<double,DirectUI::DoubleAllocationPolicy<double>,1,0>::Release(this[1]);
LABEL_57:
      v15 = v23;
LABEL_23:
      DirectUI::AccHFree(v15, v3);
      goto LABEL_11;
    }
    v24 = this[1];
    if ( v24 )
      (**(void (__fastcall ***)(DirectUI *))v24)(v24);
  }
LABEL_11:
  if ( v4 )
  {
    v10 = *(_QWORD *)(v4 + 32);
    if ( v10 )
      (*(void (__fastcall **)(__int64, DirectUI **))(*(_QWORD *)v10 + 8LL))(v10, this);
    this[3] = *(DirectUI **)(v4 + 24);
    *(_QWORD *)(v4 + 24) = this;
  }
}

```

## disassembly

```asm
0x18008638c  push    rbx
0x18008638e  push    rbp
0x18008638f  push    rsi
0x180086390  push    rdi
0x180086391  sub     rsp, 28h
0x180086395  mov     rdi, rcx
0x180086398  mov     ecx, cs:?g_dwElSlot@DirectUI@@3KA; dwTlsIndex
0x18008639e  call    cs:__imp_TlsGetValue
0x1800863a4  xor     ebp, ebp
0x1800863a6  test    rax, rax
0x1800863a9  jz      loc_180086461
0x1800863af  mov     rsi, [rax+10h]
0x1800863b3  mov     ecx, [rdi]
0x1800863b5  test    cl, 40h
0x1800863b8  jnz     short loc_1800863EC
0x1800863ba  shl     ecx, 1Ah
0x1800863bd  sar     ecx, 1Ah
0x1800863c0  cmp     ecx, 0Ch
0x1800863c3  jg      short loc_180086413
0x1800863c5  jz      loc_18008659F
0x1800863cb  sub     ecx, 4
0x1800863ce  jz      loc_180086588
0x1800863d4  sub     ecx, 1
0x1800863d7  jz      short loc_180086434
0x1800863d9  sub     ecx, 4
0x1800863dc  jz      short loc_180086455
0x1800863de  sub     ecx, 1
0x1800863e1  jz      loc_180086554
0x1800863e7  cmp     ecx, 1
0x1800863ea  jz      short loc_180086469
0x1800863ec  test    rsi, rsi
0x1800863ef  jz      short loc_18008640A
0x1800863f1  mov     rcx, [rsi+20h]
0x1800863f5  test    rcx, rcx
0x1800863f8  jnz     loc_1800865CA
0x1800863fe  mov     rax, [rsi+18h]
0x180086402  mov     [rdi+18h], rax
0x180086406  mov     [rsi+18h], rdi
0x18008640a  add     rsp, 28h
0x18008640e  pop     rdi
0x18008640f  pop     rsi
0x180086410  pop     rbp
0x180086411  pop     rbx
0x180086412  retn
0x180086413  sub     ecx, 0Dh
0x180086416  jz      short loc_180086434
0x180086418  sub     ecx, 1
0x18008641b  jz      short loc_180086444
0x18008641d  sub     ecx, 3
0x180086420  jz      loc_1800865BC
0x180086426  sub     ecx, 2
0x180086429  jz      loc_180086574
0x18008642f  cmp     ecx, 6
0x180086432  jnz     short loc_1800863EC
0x180086434  mov     rcx, [rdi+8]; this
0x180086438  test    rcx, rcx
0x18008643b  jz      short loc_1800863EC
0x18008643d  call    ?AccHFree@DirectUI@@YAXPEAX@Z; DirectUI::AccHFree(void *)
0x180086442  jmp     short loc_1800863EC
0x180086444  movzx   ecx, word ptr [rdi+8]; nAtom
0x180086448  test    cx, cx
0x18008644b  jz      short loc_1800863EC
0x18008644d  call    cs:__imp_DeleteAtom
0x180086453  jmp     short loc_1800863EC
0x180086455  cmp     byte ptr [rdi+8], 6
0x180086459  jnz     short loc_1800863EC
0x18008645b  mov     rcx, [rdi+10h]
0x18008645f  jmp     short loc_180086438
0x180086461  mov     rsi, rbp
0x180086464  jmp     loc_1800863B3
0x180086469  mov     rdx, [rdi+8]
0x18008646d  movzx   ecx, byte ptr [rdx+14h]
0x180086471  and     ecx, 7
0x180086474  jz      loc_180086512
0x18008647a  sub     ecx, 1
0x18008647d  jz      short loc_180086492
0x18008647f  sub     ecx, 1
0x180086482  jz      short loc_1800864E9
0x180086484  sub     ecx, 2
0x180086487  jz      short loc_1800864D1
0x180086489  cmp     ecx, 1
0x18008648c  jnz     loc_180086539
0x180086492  mov     rcx, [rdx]; hIcon
0x180086495  test    rcx, rcx
0x180086498  jz      short loc_1800864A6
0x18008649a  test    byte ptr [rdx+15h], 4
0x18008649e  jnz     short loc_1800864A6
0x1800864a0  call    cs:__imp_DestroyIcon
0x1800864a6  mov     rax, [rdi+8]
0x1800864aa  mov     rcx, [rax+8]; hIcon
0x1800864ae  test    rcx, rcx
0x1800864b1  jz      short loc_1800864B9
0x1800864b3  call    cs:__imp_DestroyIcon
0x1800864b9  mov     rax, [rdi+8]
0x1800864bd  mov     rcx, [rax+28h]; this
0x1800864c1  cmp     rcx, 10000h
0x1800864c8  jb      short loc_180086539
0x1800864ca  call    ?AccHFree@DirectUI@@YAXPEAX@Z; DirectUI::AccHFree(void *)
0x1800864cf  jmp     short loc_180086539
0x1800864d1  mov     rcx, [rdx]
0x1800864d4  mov     rax, [rcx]
0x1800864d7  mov     rax, [rax+10h]
0x1800864db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864e0  mov     rax, [rdi+8]
0x1800864e4  mov     [rax], rbp
0x1800864e7  jmp     short loc_180086526
0x1800864e9  mov     rcx, [rdx]; hmf
0x1800864ec  test    rcx, rcx
0x1800864ef  jz      short loc_1800864FD
0x1800864f1  test    byte ptr [rdx+15h], 4
0x1800864f5  jnz     short loc_1800864FD
0x1800864f7  call    cs:__imp_DeleteEnhMetaFile
0x1800864fd  mov     rax, [rdi+8]
0x180086501  mov     rcx, [rax+8]; hmf
0x180086505  test    rcx, rcx
0x180086508  jz      short loc_180086539
0x18008650a  call    cs:__imp_DeleteEnhMetaFile
0x180086510  jmp     short loc_180086539
0x180086512  mov     rcx, [rdx]; ho
0x180086515  test    rcx, rcx
0x180086518  jz      short loc_180086526
0x18008651a  test    byte ptr [rdx+15h], 4
0x18008651e  jnz     short loc_180086526
0x180086520  call    cs:__imp_DeleteObject
0x180086526  mov     rax, [rdi+8]
0x18008652a  mov     rcx, [rax+8]; ho
0x18008652e  test    rcx, rcx
0x180086531  jz      short loc_180086539
0x180086533  call    cs:__imp_DeleteObject
0x180086539  mov     rcx, [rdi+8]; this
0x18008653d  test    rcx, rcx
0x180086540  jz      loc_1800863EC
0x180086546  call    ?AccHFree@DirectUI@@YAXPEAX@Z; DirectUI::AccHFree(void *)
0x18008654b  mov     [rdi+8], rbp
0x18008654f  jmp     loc_1800863EC
0x180086554  mov     rbx, [rdi+8]
0x180086558  test    rbx, rbx
0x18008655b  jz      loc_1800863EC
0x180086561  mov     rax, [rbx]
0x180086564  xor     edx, edx
0x180086566  mov     rcx, rbx
0x180086569  mov     rax, [rax+40h]
0x18008656d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086572  jmp     short loc_180086580
0x180086574  mov     rbx, [rdi+8]
0x180086578  mov     rcx, rbx
0x18008657b  call    ?Release@?$DynamicArrayBase@NV?$DoubleAllocationPolicy@N@DirectUI@@$00$0A@@DirectUI@@QEAAXXZ; DirectUI::DynamicArrayBase<double,DirectUI::DoubleAllocationPolicy<double>,1,0>::Release(void)
0x180086580  mov     rcx, rbx
0x180086583  jmp     loc_18008643D
0x180086588  mov     rbx, [rdi+8]
0x18008658c  test    rbx, rbx
0x18008658f  jz      loc_1800863EC
0x180086595  mov     rcx, rbx
0x180086598  call    ?Release@?$DynamicArrayBase@NV?$DoubleAllocationPolicy@N@DirectUI@@$00$0A@@DirectUI@@QEAAXXZ; DirectUI::DynamicArrayBase<double,DirectUI::DoubleAllocationPolicy<double>,1,0>::Release(void)
0x18008659d  jmp     short loc_180086580
0x18008659f  mov     rcx, [rdi+8]
0x1800865a3  test    rcx, rcx
0x1800865a6  jz      loc_1800863EC
0x1800865ac  mov     rax, [rcx]
0x1800865af  mov     rax, [rax]
0x1800865b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865b7  jmp     loc_1800863EC
0x1800865bc  mov     rcx, [rdi+8]; this
0x1800865c0  call    ?SafeDestroyValueList@DirectUI@@YAXPEAV?$DynamicArray@PEAVValue@DirectUI@@$0A@@1@@Z; DirectUI::SafeDestroyValueList(DirectUI::DynamicArray<DirectUI::Value *,0> *)
0x1800865c5  jmp     loc_1800863EC
0x1800865ca  mov     rax, [rcx]
0x1800865cd  mov     rdx, rdi
0x1800865d0  mov     rax, [rax+8]
0x1800865d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865d9  jmp     loc_1800863FE
```
