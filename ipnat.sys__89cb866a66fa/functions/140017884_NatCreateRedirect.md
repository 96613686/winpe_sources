# NatCreateRedirect

- ea: `0x140017884`
- end: `0x1400179c3`
- name: `NatCreateRedirect`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002b38`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140017884`
- `0x1400179cc`

## pseudocode

```c
__int64 __fastcall NatCreateRedirect(int *a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  unsigned int Redirect; // eax
  unsigned int v8; // ebx
  __int128 v10; // [rsp+20h] [rbp-40h] BYREF
  __int128 v11; // [rsp+30h] [rbp-30h]
  _OWORD v12[2]; // [rsp+40h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  v6 = *a1;
  v11 = 0;
  memset(v12, 0, 28);
  DWORD1(v11) = -1;
  v10 = 0;
  LODWORD(v10) = v6;
  *((_QWORD *)&v10 + 1) = *((_QWORD *)a1 + 1);
  LODWORD(v11) = a1[4];
  BYTE8(v11) = *((_BYTE *)a1 + 20);
  HIDWORD(v11) = a1[6];
  LOWORD(v12[0]) = *((_WORD *)a1 + 14);
  DWORD1(v12[0]) = a1[8];
  WORD4(v12[0]) = *((_WORD *)a1 + 18);
  HIDWORD(v12[0]) = a1[10];
  LOWORD(v12[1]) = *((_WORD *)a1 + 22);
  DWORD1(v12[1]) = a1[12];
  WORD4(v12[1]) = *((_WORD *)a1 + 26);
  Redirect = NatCreateRedirectEx((__int64 *)&v10, a2, a3);
  v8 = Redirect;
  if ( Redirect )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids, Redirect);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140017884  push    rbp
0x140017886  push    rbx
0x140017887  push    rsi
0x140017888  push    rdi
0x140017889  push    r15
0x14001788b  mov     rbp, rsp
0x14001788e  sub     rsp, 60h
0x140017892  mov     rdi, r8
0x140017895  mov     rsi, rdx
0x140017898  mov     rbx, rcx
0x14001789b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400178a2  lea     r15, WPP_GLOBAL_Control
0x1400178a9  cmp     rcx, r15
0x1400178ac  jz      short loc_1400178D0
0x1400178ae  mov     eax, [rcx+2Ch]
0x1400178b1  test    al, 1
0x1400178b3  jz      short loc_1400178D0
0x1400178b5  cmp     byte ptr [rcx+29h], 6
0x1400178b9  jb      short loc_1400178D0
0x1400178bb  mov     rcx, [rcx+18h]
0x1400178bf  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x1400178c6  mov     edx, 18h
0x1400178cb  call    WPP_SF_
0x1400178d0  xor     eax, eax
0x1400178d2  lea     rcx, [rbp+var_40]
0x1400178d6  mov     eax, [rbx]
0x1400178d8  xorps   xmm0, xmm0
0x1400178db  movups  [rbp+var_30], xmm0
0x1400178df  mov     r8, rdi
0x1400178e2  mov     rdx, rsi
0x1400178e5  movups  [rbp+var_20], xmm0
0x1400178e9  mov     dword ptr [rbp+var_30+4], 0FFFFFFFFh
0x1400178f0  movups  [rbp+var_20+0Ch], xmm0
0x1400178f4  movups  [rbp+var_40], xmm0
0x1400178f8  mov     dword ptr [rbp+var_40], eax
0x1400178fb  mov     rax, [rbx+8]
0x1400178ff  mov     qword ptr [rbp+var_40+8], rax
0x140017903  mov     eax, [rbx+10h]
0x140017906  mov     dword ptr [rbp+var_30], eax
0x140017909  mov     al, [rbx+14h]
0x14001790c  mov     byte ptr [rbp+var_30+8], al
0x14001790f  mov     eax, [rbx+18h]
0x140017912  mov     dword ptr [rbp+var_30+0Ch], eax
0x140017915  movzx   eax, word ptr [rbx+1Ch]
0x140017919  mov     word ptr [rbp+var_20], ax
0x14001791d  mov     eax, [rbx+20h]
0x140017920  mov     dword ptr [rbp+var_20+4], eax
0x140017923  movzx   eax, word ptr [rbx+24h]
0x140017927  mov     word ptr [rbp+var_20+8], ax
0x14001792b  mov     eax, [rbx+28h]
0x14001792e  mov     dword ptr [rbp+var_20+0Ch], eax
0x140017931  movzx   eax, word ptr [rbx+2Ch]
0x140017935  mov     [rbp+var_10], ax
0x140017939  mov     eax, [rbx+30h]
0x14001793c  mov     [rbp+var_C], eax
0x14001793f  movzx   eax, word ptr [rbx+34h]
0x140017943  mov     [rbp+var_8], ax
0x140017947  call    NatCreateRedirectEx
0x14001794c  mov     ebx, eax
0x14001794e  test    eax, eax
0x140017950  jz      short loc_140017984
0x140017952  mov     rcx, cs:WPP_GLOBAL_Control
0x140017959  cmp     rcx, r15
0x14001795c  jz      short loc_1400179B5
0x14001795e  mov     edx, [rcx+2Ch]
0x140017961  test    dl, 1
0x140017964  jz      short loc_140017984
0x140017966  cmp     byte ptr [rcx+29h], 2
0x14001796a  jb      short loc_140017984
0x14001796c  mov     rcx, [rcx+18h]
0x140017970  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x140017977  mov     edx, 19h
0x14001797c  mov     r9d, eax
0x14001797f  call    WPP_SF_d
0x140017984  mov     rcx, cs:WPP_GLOBAL_Control
0x14001798b  cmp     rcx, r15
0x14001798e  jz      short loc_1400179B5
0x140017990  mov     eax, [rcx+2Ch]
0x140017993  test    al, 1
0x140017995  jz      short loc_1400179B5
0x140017997  cmp     byte ptr [rcx+29h], 6
0x14001799b  jb      short loc_1400179B5
0x14001799d  mov     rcx, [rcx+18h]
0x1400179a1  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x1400179a8  mov     edx, 1Ah
0x1400179ad  mov     r9d, ebx
0x1400179b0  call    WPP_SF_d
0x1400179b5  mov     eax, ebx
0x1400179b7  add     rsp, 60h
0x1400179bb  pop     r15
0x1400179bd  pop     rdi
0x1400179be  pop     rsi
0x1400179bf  pop     rbx
0x1400179c0  pop     rbp
0x1400179c1  retn
```
