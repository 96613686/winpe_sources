# COskNativeHWNDHost::Create(DirectUI::NativeHWNDHost * *)

- ea: `0x1400144fc`
- end: `0x14001462d`
- name: `?Create@COskNativeHWNDHost@@SAJPEAPEAVNativeHWNDHost@DirectUI@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct DirectUI::NativeHWNDHost **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140007f54`

## callees

- `0x14000ee88`
- `0x1400144fc`
- `0x140014f60`
- `0x140025d70`

## import_xrefs

- `USER32!LoadStringW` at `0x1400145af`
- `USER32!LoadStringW` at `0x1400145af`
- `USER32!LoadIconW` at `0x1400145c1`
- `USER32!LoadIconW` at `0x1400145c1`
- `DUI70!??0NativeHWNDHost@DirectUI@@QEAA@XZ` at `0x14001454a`
- `DUI70!??0NativeHWNDHost@DirectUI@@QEAA@XZ` at `0x14001454a`
- `DUI70!?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x1400145eb`
- `DUI70!?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x1400145eb`

## pseudocode

```c
__int64 __fastcall COskNativeHWNDHost::Create(struct DirectUI::NativeHWNDHost **a1, unsigned __int64 a2)
{
  DirectUI::NativeHWNDHost *v3; // rax
  DirectUI::NativeHWNDHost *v4; // rbx
  HICON IconW; // rax
  const unsigned __int16 *v6; // rdx
  HWND v7; // r9
  int v8; // edi
  WCHAR Buffer[264]; // [rsp+70h] [rbp-228h] BYREF

  if ( COskNativeHWNDHost::s_pThis )
  {
    v8 = 0;
  }
  else
  {
    v3 = (DirectUI::NativeHWNDHost *)DirectUI::HAllocAndZero((DirectUI *)0x88, a2);
    v4 = v3;
    if ( v3 )
    {
      DirectUI::NativeHWNDHost::NativeHWNDHost(v3);
      *((_QWORD *)v4 + 9) = 0;
      *((_WORD *)v4 + 51) = 0;
      *(_QWORD *)v4 = &COskNativeHWNDHost::`vftable'{for `DirectUI::NativeHWNDHost'};
      *((_DWORD *)v4 + 30) = 0;
      *((_QWORD *)v4 + 6) = &COskNativeHWNDHost::`vftable'{for `IAccessibilityDockingServiceCallback'};
      *((_WORD *)v4 + 62) = 0;
      *((_BYTE *)v4 + 80) = 0;
      *((_BYTE *)v4 + 100) = 1;
      *((_QWORD *)v4 + 16) = 0;
      *(_QWORD *)((char *)v4 + 84) = 0;
      *(_QWORD *)((char *)v4 + 92) = 0;
      Buffer[0] = 0;
      LoadStringW(g_hInstance, 0x3E8u, Buffer, 260);
      IconW = LoadIconW(g_hInstance, (LPCWSTR)1);
      v8 = COskNativeHWNDHost::Initialize(v4, v6, Buffer, v7, IconW);
      if ( v8 < 0 )
        DirectUI::NativeHWNDHost::Destroy(v4);
      else
        COskNativeHWNDHost::s_pThis = v4;
    }
    else
    {
      v8 = -2147024882;
    }
  }
  *a1 = COskNativeHWNDHost::s_pThis;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400144fc  mov     [rsp+arg_8], rbx
0x140014501  mov     [rsp+arg_10], rsi
0x140014506  push    rdi
0x140014507  sub     rsp, 290h
0x14001450e  mov     rax, cs:__security_cookie
0x140014515  xor     rax, rsp
0x140014518  mov     [rsp+298h+var_18], rax
0x140014520  cmp     cs:?s_pThis@COskNativeHWNDHost@@1PEAV1@EA, 0; COskNativeHWNDHost * COskNativeHWNDHost::s_pThis
0x140014528  mov     rsi, rcx
0x14001452b  jnz     loc_1400145FA
0x140014531  mov     ecx, 88h; this
0x140014536  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x14001453b  mov     rbx, rax
0x14001453e  test    rax, rax
0x140014541  jz      loc_1400145F3
0x140014547  mov     rcx, rax
0x14001454a  call    cs:__imp_??0NativeHWNDHost@DirectUI@@QEAA@XZ; DirectUI::NativeHWNDHost::NativeHWNDHost(void)
0x140014550  xor     ecx, ecx
0x140014552  mov     qword ptr [rbx+48h], 0
0x14001455a  mov     [rbx+66h], cx
0x14001455e  lea     rax, ??_7COskNativeHWNDHost@@6BNativeHWNDHost@DirectUI@@@; const COskNativeHWNDHost::`vftable'{for `DirectUI::NativeHWNDHost'}
0x140014565  mov     [rbx], rax
0x140014568  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x14001456d  mov     [rbx+78h], ecx
0x140014570  lea     rax, ??_7COskNativeHWNDHost@@6BIAccessibilityDockingServiceCallback@@@; const COskNativeHWNDHost::`vftable'{for `IAccessibilityDockingServiceCallback'}
0x140014577  mov     [rbx+30h], rax
0x14001457b  mov     r9d, 104h; cchBufferMax
0x140014581  mov     [rbx+7Ch], cx
0x140014585  xor     eax, eax
0x140014587  mov     byte ptr [rbx+50h], 0
0x14001458b  mov     edx, 3E8h; uID
0x140014590  mov     byte ptr [rbx+64h], 1
0x140014594  mov     [rbx+80h], rcx
0x14001459b  mov     [rbx+54h], rcx
0x14001459f  mov     [rbx+5Ch], rcx
0x1400145a3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1400145aa  mov     [rsp+298h+Buffer], ax
0x1400145af  call    cs:__imp_LoadStringW
0x1400145b5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1400145bc  mov     edx, 1; lpIconName
0x1400145c1  call    cs:__imp_LoadIconW
0x1400145c7  lea     r8, [rsp+298h+Buffer]; unsigned __int16 *
0x1400145cc  mov     rcx, rbx; this
0x1400145cf  mov     [rsp+298h+var_278], rax; HICON
0x1400145d4  call    ?Initialize@COskNativeHWNDHost@@AEAAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@I@Z; COskNativeHWNDHost::Initialize(ushort const *,ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,HINSTANCE__ *,uint)
0x1400145d9  mov     edi, eax
0x1400145db  test    eax, eax
0x1400145dd  js      short loc_1400145E8
0x1400145df  mov     cs:?s_pThis@COskNativeHWNDHost@@1PEAV1@EA, rbx; COskNativeHWNDHost * COskNativeHWNDHost::s_pThis
0x1400145e6  jmp     short loc_1400145FC
0x1400145e8  mov     rcx, rbx
0x1400145eb  call    cs:__imp_?Destroy@NativeHWNDHost@DirectUI@@QEAAXXZ; DirectUI::NativeHWNDHost::Destroy(void)
0x1400145f1  jmp     short loc_1400145FC
0x1400145f3  mov     edi, 8007000Eh
0x1400145f8  jmp     short loc_1400145FC
0x1400145fa  xor     edi, edi
0x1400145fc  mov     rax, cs:?s_pThis@COskNativeHWNDHost@@1PEAV1@EA; COskNativeHWNDHost * COskNativeHWNDHost::s_pThis
0x140014603  mov     [rsi], rax
0x140014606  mov     eax, edi
0x140014608  mov     rcx, [rsp+298h+var_18]
0x140014610  xor     rcx, rsp; StackCookie
0x140014613  call    __security_check_cookie
0x140014618  lea     r11, [rsp+298h+var_8]
0x140014620  mov     rbx, [r11+18h]
0x140014624  mov     rsi, [r11+20h]
0x140014628  mov     rsp, r11
0x14001462b  pop     rdi
0x14001462c  retn
```
