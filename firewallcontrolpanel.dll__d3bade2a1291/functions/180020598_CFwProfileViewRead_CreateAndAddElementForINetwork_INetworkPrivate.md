# CFwProfileViewRead::CreateAndAddElementForINetwork(INetworkPrivate *)

- ea: `0x180020598`
- end: `0x1800206a9`
- name: `?CreateAndAddElementForINetwork@CFwProfileViewRead@@AEAAJPEAUINetworkPrivate@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(CFwProfileViewRead *__hidden this, struct INetworkPrivate *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800212e4`

## callees

- `0x18000994c`
- `0x180020598`
- `0x1800206b0`
- `0x180020aec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020686`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x180020655`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x180020655`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180020694`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180020694`

## pseudocode

```c
__int64 __fastcall CFwProfileViewRead::CreateAndAddElementForINetwork(
        CFwProfileViewRead *this,
        struct INetworkPrivate *a2)
{
  __int64 v2; // rax
  struct DirectUI::Value *Graphic; // rdi
  CFwProfileViewRead *v6; // rcx
  int IconForNetwork; // ebx
  CFwCplLua *v8; // rcx
  __int64 v9; // rdx
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF
  HICON v12; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a2;
  pv = 0;
  v12 = 0;
  Graphic = 0;
  IconForNetwork = (*(__int64 (__fastcall **)(struct INetworkPrivate *, LPVOID *))(v2 + 24))(a2, &pv);
  if ( IconForNetwork >= 0 )
  {
    IconForNetwork = CFwProfileViewRead::GetIconForNetwork(v6, a2, &v12);
    if ( IconForNetwork >= 0 )
    {
      if ( !v12 || (Graphic = DirectUI::Value::CreateGraphic(v12, 0, 0, 0)) != 0 )
        IconForNetwork = CFwProfileViewRead::CreateAndAddNetworkElement(this, (const unsigned __int16 *)pv, Graphic);
      else
        IconForNetwork = -2147024882;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 27;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 26;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids, (unsigned int)IconForNetwork);
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( Graphic )
    DirectUI::Value::Release(Graphic);
  return (unsigned int)IconForNetwork;
}

```

## disassembly

```asm
0x180020598  mov     r11, rsp
0x18002059b  mov     [r11+8], rbx
0x18002059f  push    rbp
0x1800205a0  push    rsi
0x1800205a1  push    rdi
0x1800205a2  sub     rsp, 20h
0x1800205a6  mov     rax, [rdx]
0x1800205a9  mov     rsi, rdx
0x1800205ac  mov     rbp, rcx
0x1800205af  mov     qword ptr [r11+10h], 0
0x1800205b7  lea     rdx, [r11+10h]
0x1800205bb  mov     qword ptr [r11+18h], 0
0x1800205c3  mov     rcx, rsi
0x1800205c6  xor     edi, edi
0x1800205c8  mov     rax, [rax+18h]
0x1800205cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205d1  mov     ebx, eax
0x1800205d3  test    eax, eax
0x1800205d5  jns     short loc_180020610
0x1800205d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205de  lea     rax, WPP_GLOBAL_Control
0x1800205e5  cmp     rcx, rax
0x1800205e8  jz      loc_18002067C
0x1800205ee  test    byte ptr [rcx+1Ch], 1
0x1800205f2  jz      loc_18002067C
0x1800205f8  lea     edx, [rdi+1Ah]
0x1800205fb  mov     rcx, [rcx+10h]
0x1800205ff  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020606  mov     r9d, ebx
0x180020609  call    WPP_SF_d
0x18002060e  jmp     short loc_18002067C
0x180020610  lea     r8, [rsp+38h+arg_10]; HICON *
0x180020615  mov     rdx, rsi; struct INetworkPrivate *
0x180020618  call    ?GetIconForNetwork@CFwProfileViewRead@@AEAAJPEAUINetworkPrivate@@PEAPEAUHICON__@@@Z; CFwProfileViewRead::GetIconForNetwork(INetworkPrivate *,HICON__ * *)
0x18002061d  mov     ebx, eax
0x18002061f  test    eax, eax
0x180020621  jns     short loc_180020643
0x180020623  mov     rcx, cs:WPP_GLOBAL_Control
0x18002062a  lea     rax, WPP_GLOBAL_Control
0x180020631  cmp     rcx, rax
0x180020634  jz      short loc_18002067C
0x180020636  test    byte ptr [rcx+1Ch], 1
0x18002063a  jz      short loc_18002067C
0x18002063c  mov     edx, 1Bh
0x180020641  jmp     short loc_1800205FB
0x180020643  mov     rcx, [rsp+38h+arg_10]
0x180020648  test    rcx, rcx
0x18002064b  jz      short loc_18002066A
0x18002064d  xor     r9d, r9d
0x180020650  xor     r8d, r8d
0x180020653  xor     edx, edx
0x180020655  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x18002065b  mov     rdi, rax
0x18002065e  test    rax, rax
0x180020661  jnz     short loc_18002066A
0x180020663  mov     ebx, 8007000Eh
0x180020668  jmp     short loc_18002067C
0x18002066a  mov     rdx, [rsp+38h+pv]; unsigned __int16 *
0x18002066f  mov     r8, rdi; struct DirectUI::Value *
0x180020672  mov     rcx, rbp; this
0x180020675  call    ?CreateAndAddNetworkElement@CFwProfileViewRead@@AEAAJPEBGPEAVValue@DirectUI@@@Z; CFwProfileViewRead::CreateAndAddNetworkElement(ushort const *,DirectUI::Value *)
0x18002067a  mov     ebx, eax
0x18002067c  mov     rcx, [rsp+38h+pv]; pv
0x180020681  test    rcx, rcx
0x180020684  jz      short loc_18002068C
0x180020686  call    cs:__imp_CoTaskMemFree
0x18002068c  test    rdi, rdi
0x18002068f  jz      short loc_18002069A
0x180020691  mov     rcx, rdi
0x180020694  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002069a  mov     eax, ebx
0x18002069c  mov     rbx, [rsp+38h+arg_0]
0x1800206a1  add     rsp, 20h
0x1800206a5  pop     rdi
0x1800206a6  pop     rsi
0x1800206a7  pop     rbp
0x1800206a8  retn
```
