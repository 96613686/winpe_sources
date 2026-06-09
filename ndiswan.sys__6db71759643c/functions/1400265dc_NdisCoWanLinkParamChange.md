# NdisCoWanLinkParamChange

- ea: `0x1400265dc`
- end: `0x1400267ed`
- name: `NdisCoWanLinkParamChange`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140007560`

## callees

- `0x140007364`
- `0x14000b1fc`
- `0x14000b25c`
- `0x1400265dc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400267d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400267d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026613`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400266bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026613`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400266bd`

## pseudocode

```c
void __fastcall NdisCoWanLinkParamChange(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4, int a5)
{
  _DWORD *v8; // r8
  int *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  char v12; // cl
  int v13; // eax

  if ( a5 == 1073807382 )
  {
    if ( a4 < 0xC )
      return;
    *(_BYTE *)(a2 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 1768));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_ddd(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_dbbcdfd2b1703828b2981634423cad5f_Traceguids,
        (unsigned int)a3[2],
        *a3,
        a3[1]);
    }
    v8 = (_DWORD *)(a1 + 208);
    *(_DWORD *)(a1 + 208) = a3[2];
    v9 = (int *)(a1 + 136);
    *(_DWORD *)(a1 + 136) = *a3;
    *(_DWORD *)(a1 + 168) = a3[1];
  }
  else
  {
    if ( a4 < 0x14 || (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 72) + 124LL) - 13) > 1 && *a3 != 1 )
      return;
    *(_BYTE *)(a2 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 1768));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, v10, v11, (unsigned int)a3[3], a3[1], a3[2], a3[4]);
    }
    v8 = (_DWORD *)(a1 + 208);
    *(_DWORD *)(a1 + 208) = a3[3];
    v9 = (int *)(a1 + 136);
    *(_DWORD *)(a1 + 136) = a3[1];
    *(_DWORD *)(a1 + 168) = a3[2];
    *(_DWORD *)(a1 + 152) = a3[4];
    *(_DWORD *)(a1 + 184) = a3[4];
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 72) + 124LL) - 13) <= 1 )
      *(_DWORD *)(a2 + 1788) = *a3;
  }
  if ( *(_BYTE *)(a1 + 200) )
  {
    v12 = *(_BYTE *)(a1 + 201);
    if ( *v8 > *(_DWORD *)(a1 + 212) )
    {
      if ( !v12 )
      {
        *(_BYTE *)(a1 + 201) = 1;
        ++*(_DWORD *)(a2 + 156);
      }
    }
    else if ( v12 )
    {
      *(_BYTE *)(a1 + 201) = 0;
      --*(_DWORD *)(a2 + 156);
    }
  }
  v13 = *v9;
  if ( !*v9 )
  {
    v13 = 3600;
    *v9 = 3600;
  }
  if ( !*(_DWORD *)(a1 + 168) )
    *(_DWORD *)(a1 + 168) = v13;
  UpdateBundleInfo(a2);
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 1768), *(_BYTE *)(a2 + 1776));
}

```

## disassembly

```asm
0x1400265dc  mov     [rsp+arg_0], rbx
0x1400265e1  mov     [rsp+arg_8], rsi
0x1400265e6  push    rdi
0x1400265e7  sub     rsp, 40h
0x1400265eb  cmp     [rsp+48h+arg_20], 40010016h
0x1400265f3  mov     rsi, r8
0x1400265f6  mov     rdi, rdx
0x1400265f9  mov     rbx, rcx
0x1400265fc  jnz     loc_140026693
0x140026602  cmp     r9d, 0Ch
0x140026606  jb      loc_1400267DC
0x14002660c  lea     rcx, [rdx+6E8h]; SpinLock
0x140026613  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002661a  nop     dword ptr [rax+rax+00h]
0x14002661f  mov     [rdi+6F0h], al
0x140026625  mov     rcx, cs:WPP_GLOBAL_Control
0x14002662c  lea     rax, WPP_GLOBAL_Control
0x140026633  cmp     rcx, rax
0x140026636  jz      short loc_14002666D
0x140026638  test    dword ptr [rcx+2Ch], 20000h
0x14002663f  jz      short loc_14002666D
0x140026641  cmp     byte ptr [rcx+29h], 5
0x140026645  jb      short loc_14002666D
0x140026647  mov     eax, [rsi+4]
0x14002664a  lea     r8, WPP_dbbcdfd2b1703828b2981634423cad5f_Traceguids
0x140026651  mov     r9d, [rsi+8]
0x140026655  mov     edx, 0Bh
0x14002665a  mov     rcx, [rcx+18h]
0x14002665e  mov     [rsp+48h+var_20], eax
0x140026662  mov     eax, [rsi]
0x140026664  mov     [rsp+48h+var_28], eax
0x140026668  call    WPP_SF_ddd
0x14002666d  mov     eax, [rsi+8]
0x140026670  lea     r8, [rbx+0D0h]
0x140026677  mov     [r8], eax
0x14002667a  lea     rdx, [rbx+88h]
0x140026681  mov     eax, [rsi]
0x140026683  mov     [rdx], eax
0x140026685  mov     eax, [rsi+4]
0x140026688  mov     [rbx+0A8h], eax
0x14002668e  jmp     loc_14002675E
0x140026693  cmp     r9d, 14h
0x140026697  jb      loc_1400267DC
0x14002669d  mov     rax, [rcx+48h]
0x1400266a1  mov     ecx, [rax+7Ch]
0x1400266a4  sub     ecx, 0Dh
0x1400266a7  cmp     ecx, 1
0x1400266aa  jbe     short loc_1400266B6
0x1400266ac  cmp     dword ptr [r8], 1
0x1400266b0  jnz     loc_1400267DC
0x1400266b6  lea     rcx, [rdx+6E8h]; SpinLock
0x1400266bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400266c4  nop     dword ptr [rax+rax+00h]
0x1400266c9  mov     [rdi+6F0h], al
0x1400266cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266d6  lea     rax, WPP_GLOBAL_Control
0x1400266dd  cmp     rcx, rax
0x1400266e0  jz      short loc_140026713
0x1400266e2  test    dword ptr [rcx+2Ch], 20000h
0x1400266e9  jz      short loc_140026713
0x1400266eb  cmp     byte ptr [rcx+29h], 5
0x1400266ef  jb      short loc_140026713
0x1400266f1  mov     eax, [rsi+10h]
0x1400266f4  mov     r9d, [rsi+0Ch]
0x1400266f8  mov     rcx, [rcx+18h]
0x1400266fc  mov     [rsp+48h+var_18], eax
0x140026700  mov     eax, [rsi+8]
0x140026703  mov     [rsp+48h+var_20], eax
0x140026707  mov     eax, [rsi+4]
0x14002670a  mov     [rsp+48h+var_28], eax
0x14002670e  call    WPP_SF_dddd
0x140026713  mov     eax, [rsi+0Ch]
0x140026716  lea     r8, [rbx+0D0h]
0x14002671d  mov     [r8], eax
0x140026720  lea     rdx, [rbx+88h]
0x140026727  mov     eax, [rsi+4]
0x14002672a  mov     [rdx], eax
0x14002672c  mov     eax, [rsi+8]
0x14002672f  mov     [rbx+0A8h], eax
0x140026735  mov     eax, [rsi+10h]
0x140026738  mov     [rbx+98h], eax
0x14002673e  mov     eax, [rsi+10h]
0x140026741  mov     [rbx+0B8h], eax
0x140026747  mov     rax, [rbx+48h]
0x14002674b  mov     ecx, [rax+7Ch]
0x14002674e  sub     ecx, 0Dh
0x140026751  cmp     ecx, 1
0x140026754  ja      short loc_14002675E
0x140026756  mov     eax, [rsi]
0x140026758  mov     [rdi+6FCh], eax
0x14002675e  xor     r9d, r9d
0x140026761  cmp     [rbx+0C8h], r9b
0x140026768  jz      short loc_14002679F
0x14002676a  mov     eax, [rbx+0D4h]
0x140026770  mov     cl, [rbx+0C9h]
0x140026776  cmp     [r8], eax
0x140026779  ja      short loc_14002678E
0x14002677b  test    cl, cl
0x14002677d  jz      short loc_14002679F
0x14002677f  mov     [rbx+0C9h], r9b
0x140026786  dec     dword ptr [rdi+9Ch]
0x14002678c  jmp     short loc_14002679F
0x14002678e  test    cl, cl
0x140026790  jnz     short loc_14002679F
0x140026792  mov     byte ptr [rbx+0C9h], 1
0x140026799  inc     dword ptr [rdi+9Ch]
0x14002679f  mov     eax, [rdx]
0x1400267a1  test    eax, eax
0x1400267a3  jnz     short loc_1400267AC
0x1400267a5  mov     eax, 0E10h
0x1400267aa  mov     [rdx], eax
0x1400267ac  cmp     [rbx+0A8h], r9d
0x1400267b3  jnz     short loc_1400267BB
0x1400267b5  mov     [rbx+0A8h], eax
0x1400267bb  mov     rcx, rdi
0x1400267be  call    UpdateBundleInfo
0x1400267c3  mov     dl, [rdi+6F0h]; NewIrql
0x1400267c9  lea     rcx, [rdi+6E8h]; SpinLock
0x1400267d0  call    cs:__imp_KeReleaseSpinLock
0x1400267d7  nop     dword ptr [rax+rax+00h]
0x1400267dc  mov     rbx, [rsp+48h+arg_0]
0x1400267e1  mov     rsi, [rsp+48h+arg_8]
0x1400267e6  add     rsp, 40h
0x1400267ea  pop     rdi
0x1400267eb  retn
```
