# PxClMakeCallComplete

- ea: `0x14000fcb0`
- end: `0x14001009e`
- name: `PxClMakeCallComplete`
- size: `1006`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140013bc0`

## callees

- `0x140001bc8`
- `0x140001c0c`
- `0x140001c60`
- `0x140006e08`
- `0x140007040`
- `0x140007fc0`
- `0x14000fcb0`
- `0x140011d30`
- `0x1400156d8`
- `0x140016450`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ff0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ff0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fef2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001006d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fef2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001006d`

## pseudocode

```c
void __fastcall PxClMakeCallComplete(int a1, unsigned __int64 a2)
{
  int v3; // ebx
  _DWORD *v4; // rdi
  unsigned int v5; // eax
  unsigned int v6; // esi
  int v7; // ecx
  unsigned int v8; // ebp
  char v9; // al
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  PVOID Entry; // [rsp+40h] [rbp-68h] BYREF
  _QWORD Src[6]; // [rsp+48h] [rbp-60h] BYREF

  Entry = 0;
  v3 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2, a1);
  GetVcFromCtx(a2, &Entry);
  v4 = Entry;
  if ( Entry )
  {
    *((_BYTE *)v4 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
    v5 = v4[8];
    if ( (v5 & 0x100) != 0 )
    {
LABEL_34:
      if ( v4[7]-- == 1 )
        DoDerefVcWork(v4);
      else
        KeReleaseSpinLock((PKSPIN_LOCK)v4 + 64, *((_BYTE *)v4 + 520));
      return;
    }
    v6 = 128;
    if ( (v5 & 0x80) != 0 )
    {
      v5 = v5 & 0xFFFFFE7F | 0x100;
      v4[8] = v5;
    }
    if ( !v3 )
    {
      v7 = v4[4];
      if ( v7 == 3 )
      {
        v4[8] = v5 & 0xFFFFFEFF;
        v8 = 0;
        PxCloseCallWithCm(v4);
        v9 = 0;
      }
      else
      {
        v4[5] = v7;
        v9 = 1;
        v4[4] = 4;
        v8 = 256;
      }
      if ( v9 != 1 )
      {
LABEL_32:
        if ( (v4[8] & 0x10) != 0 )
          PxTapiCompleteDropIrps((__int64)v4);
        goto LABEL_34;
      }
      v6 = 0;
LABEL_28:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
          v4,
          v8,
          v6,
          *(_DWORD *)(*((_QWORD *)v4 + 38) + 32LL));
      v10 = *((_QWORD *)v4 + 32);
      Src[2] = 2;
      v11 = *(_QWORD *)(v10 + 40);
      Src[1] = *((_QWORD *)v4 + 34);
      Src[0] = v11;
      Src[3] = v8;
      Src[4] = v6;
      v12 = *(unsigned int *)(*((_QWORD *)v4 + 38) + 32LL);
      v4[73] = v8;
      Src[5] = v12;
      v4[74] = v6;
      KeReleaseSpinLock((PKSPIN_LOCK)v4 + 64, *((_BYTE *)v4 + 520));
      PxIndicateStatus(Src);
      *((_BYTE *)v4 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v4 + 64);
      goto LABEL_32;
    }
    v8 = 0x4000;
    if ( v3 > -1073668060 )
    {
      if ( v3 <= -1073668054 )
      {
        switch ( v3 )
        {
          case -1073668054:
            v6 = 1024;
            goto LABEL_27;
          case -1073668059:
            goto LABEL_64;
          case -1073668058:
LABEL_51:
            v6 = 64;
            goto LABEL_27;
          case -1073668057:
            goto LABEL_27;
        }
        if ( v3 != -1073668056 )
        {
LABEL_49:
          v6 = 512;
          goto LABEL_27;
        }
        goto LABEL_50;
      }
      if ( v3 == -1073668053 )
        goto LABEL_26;
      if ( v3 != 65539 )
      {
        if ( v3 == 65543 )
          goto LABEL_64;
        goto LABEL_56;
      }
    }
    else
    {
      if ( v3 == -1073668060 )
      {
        v6 = 16;
        goto LABEL_27;
      }
      if ( v3 <= -1073676247 )
      {
        if ( v3 != -1073676247 )
        {
          if ( v3 != -1073741823 )
          {
            if ( v3 != -1073741670 )
            {
              if ( v3 != -1073676255 )
              {
                if ( v3 == -1073676254 )
                {
LABEL_27:
                  --v4[7];
                  v4[5] = v4[4];
                  v4[4] = 0;
                  goto LABEL_28;
                }
                if ( v3 == -1073676252 )
                {
LABEL_26:
                  v6 = 2048;
                  goto LABEL_27;
                }
                goto LABEL_56;
              }
LABEL_64:
              v6 = 32;
              goto LABEL_27;
            }
            goto LABEL_49;
          }
LABEL_56:
          v6 = 2;
          if ( *(_DWORD *)(*((_QWORD *)v4 + 11) + 172LL) != 13 )
            goto LABEL_27;
          if ( v3 != -2147024775 )
          {
            if ( v3 == -1073741247 )
            {
              v6 = 0x80000;
              goto LABEL_27;
            }
            if ( v3 != 121 )
            {
              if ( (v3 & 0xFFFF0000) == 0 )
                v3 |= 0x80070000;
              v6 = v3;
              goto LABEL_27;
            }
          }
          goto LABEL_51;
        }
LABEL_50:
        v6 = 256;
        goto LABEL_27;
      }
      if ( v3 == -1073668064 )
      {
        v6 = 1;
        goto LABEL_27;
      }
      if ( v3 == -1073668063 )
        goto LABEL_56;
      if ( v3 != -1073668062 )
      {
        if ( v3 == -1073668061 )
        {
          v6 = 8;
          goto LABEL_27;
        }
        goto LABEL_56;
      }
    }
    v6 = 4;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)((_DWORD)Entry + 26),
      WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
      a2);
}

```

## disassembly

```asm
0x14000fcb0  mov     [rsp+arg_10], rbx
0x14000fcb5  push    rbp
0x14000fcb6  push    rsi
0x14000fcb7  push    rdi
0x14000fcb8  push    r12
0x14000fcba  push    r14
0x14000fcbc  sub     rsp, 80h
0x14000fcc3  mov     rax, cs:__security_cookie
0x14000fcca  xor     rax, rsp
0x14000fccd  mov     [rsp+0A8h+var_30], rax
0x14000fcd2  mov     rsi, rdx
0x14000fcd5  mov     [rsp+0A8h+Entry], 0
0x14000fcde  mov     ebx, ecx
0x14000fce0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fce7  lea     r12, WPP_GLOBAL_Control
0x14000fcee  cmp     rcx, r12
0x14000fcf1  jz      short loc_14000FD15
0x14000fcf3  cmp     byte ptr [rcx+29h], 5
0x14000fcf7  jb      short loc_14000FD15
0x14000fcf9  mov     rcx, [rcx+18h]
0x14000fcfd  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000fd04  mov     edx, 19h
0x14000fd09  mov     [rsp+0A8h+var_88], ebx
0x14000fd0d  mov     r9, rsi
0x14000fd10  call    WPP_SF_qD
0x14000fd15  lea     rdx, [rsp+0A8h+Entry]
0x14000fd1a  mov     rcx, rsi
0x14000fd1d  call    GetVcFromCtx
0x14000fd22  mov     rdi, [rsp+0A8h+Entry]
0x14000fd27  test    rdi, rdi
0x14000fd2a  jnz     short loc_14000FD61
0x14000fd2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd33  cmp     rcx, r12
0x14000fd36  jz      loc_140010079
0x14000fd3c  cmp     byte ptr [rcx+29h], 3
0x14000fd40  jb      loc_140010079
0x14000fd46  mov     rcx, [rcx+18h]
0x14000fd4a  lea     edx, [rdi+1Ah]
0x14000fd4d  mov     r9, rsi
0x14000fd50  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000fd57  call    WPP_SF_q
0x14000fd5c  jmp     loc_140010079
0x14000fd61  lea     r14, [rdi+200h]
0x14000fd68  mov     rcx, r14; SpinLock
0x14000fd6b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fd72  nop     dword ptr [rax+rax+00h]
0x14000fd77  mov     [rdi+208h], al
0x14000fd7d  mov     edx, 100h
0x14000fd82  mov     eax, [rdi+20h]
0x14000fd85  test    edx, eax
0x14000fd87  jnz     loc_14000FF2C
0x14000fd8d  lea     esi, [rdx-80h]
0x14000fd90  test    sil, al
0x14000fd93  jz      short loc_14000FD9E
0x14000fd95  btr     eax, 7
0x14000fd99  or      eax, edx
0x14000fd9b  mov     [rdi+20h], eax
0x14000fd9e  mov     ecx, 2
0x14000fda3  test    ebx, ebx
0x14000fda5  jnz     short loc_14000FDE3
0x14000fda7  mov     ecx, [rdi+10h]
0x14000fdaa  lea     esi, [rbx+1]
0x14000fdad  cmp     ecx, 3
0x14000fdb0  jnz     short loc_14000FDC7
0x14000fdb2  btr     eax, 8
0x14000fdb6  mov     rcx, rdi
0x14000fdb9  mov     [rdi+20h], eax
0x14000fdbc  xor     ebp, ebp
0x14000fdbe  call    PxCloseCallWithCm
0x14000fdc3  xor     al, al
0x14000fdc5  jmp     short loc_14000FDD6
0x14000fdc7  mov     [rdi+14h], ecx
0x14000fdca  mov     al, sil
0x14000fdcd  mov     dword ptr [rdi+10h], 4
0x14000fdd4  mov     ebp, edx
0x14000fdd6  cmp     al, sil
0x14000fdd9  jnz     loc_14000FF1D
0x14000fddf  xor     esi, esi
0x14000fde1  jmp     short loc_14000FE5B
0x14000fde3  mov     eax, 0C0012024h
0x14000fde8  mov     ebp, 4000h
0x14000fded  cmp     ebx, eax
0x14000fdef  jg      loc_14000FF8D
0x14000fdf5  jz      loc_14000FF83
0x14000fdfb  mov     eax, 0C0010029h
0x14000fe00  cmp     ebx, eax
0x14000fe02  jg      loc_14000FF43
0x14000fe08  jz      loc_14000FFD2
0x14000fe0e  cmp     ebx, 0C0000001h
0x14000fe14  jz      loc_140010009
0x14000fe1a  cmp     ebx, 0C000009Ah
0x14000fe20  jz      loc_14000FFC8
0x14000fe26  cmp     ebx, 0C0010021h
0x14000fe2c  jz      loc_140010050
0x14000fe32  cmp     ebx, 0C0010022h
0x14000fe38  jz      short loc_14000FE4B
0x14000fe3a  cmp     ebx, 0C0010024h
0x14000fe40  jnz     loc_140010009
0x14000fe46  mov     esi, 800h
0x14000fe4b  dec     dword ptr [rdi+1Ch]
0x14000fe4e  mov     eax, [rdi+10h]
0x14000fe51  mov     [rdi+14h], eax
0x14000fe54  mov     dword ptr [rdi+10h], 0
0x14000fe5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe62  cmp     rcx, r12
0x14000fe65  jz      short loc_14000FE9B
0x14000fe67  cmp     byte ptr [rcx+29h], 5
0x14000fe6b  jb      short loc_14000FE9B
0x14000fe6d  mov     rax, [rdi+130h]
0x14000fe74  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000fe7b  mov     rcx, [rcx+18h]
0x14000fe7f  mov     edx, 1Bh
0x14000fe84  mov     r9, rdi
0x14000fe87  mov     eax, [rax+20h]
0x14000fe8a  mov     [rsp+0A8h+var_78], eax
0x14000fe8e  mov     [rsp+0A8h+var_80], esi
0x14000fe92  mov     [rsp+0A8h+var_88], ebp
0x14000fe96  call    WPP_SF_qDDD
0x14000fe9b  mov     rax, [rdi+100h]
0x14000fea2  mov     [rsp+0A8h+var_50], 2
0x14000feab  mov     rcx, [rax+28h]
0x14000feaf  mov     rax, [rdi+110h]
0x14000feb6  mov     [rsp+0A8h+var_58], rax
0x14000febb  mov     [rsp+0A8h+Src], rcx
0x14000fec0  mov     eax, ebp
0x14000fec2  mov     [rsp+0A8h+var_48], rax
0x14000fec7  mov     eax, esi
0x14000fec9  mov     [rsp+0A8h+var_40], rax
0x14000fece  mov     rax, [rdi+130h]
0x14000fed5  mov     ecx, [rax+20h]
0x14000fed8  mov     [rdi+124h], ebp
0x14000fede  mov     [rsp+0A8h+var_38], rcx
0x14000fee3  mov     rcx, r14; SpinLock
0x14000fee6  mov     [rdi+128h], esi
0x14000feec  mov     dl, [rdi+208h]; NewIrql
0x14000fef2  call    cs:__imp_KeReleaseSpinLock
0x14000fef9  nop     dword ptr [rax+rax+00h]
0x14000fefe  lea     rcx, [rsp+0A8h+Src]; Src
0x14000ff03  call    PxIndicateStatus
0x14000ff08  mov     rcx, r14; SpinLock
0x14000ff0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ff12  nop     dword ptr [rax+rax+00h]
0x14000ff17  mov     [rdi+208h], al
0x14000ff1d  mov     eax, [rdi+20h]
0x14000ff20  test    al, 10h
0x14000ff22  jz      short loc_14000FF2C
0x14000ff24  mov     rcx, rdi
0x14000ff27  call    PxTapiCompleteDropIrps
0x14000ff2c  add     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x14000ff30  jnz     loc_140010064
0x14000ff36  mov     rcx, rdi; Entry
0x14000ff39  call    DoDerefVcWork
0x14000ff3e  jmp     loc_140010079
0x14000ff43  cmp     ebx, 0C0012020h
0x14000ff49  jz      short loc_14000FF79
0x14000ff4b  cmp     ebx, 0C0012021h
0x14000ff51  jz      loc_140010009
0x14000ff57  cmp     ebx, 0C0012022h
0x14000ff5d  jz      loc_14001005A
0x14000ff63  cmp     ebx, 0C0012023h
0x14000ff69  jnz     loc_140010009
0x14000ff6f  mov     esi, 8
0x14000ff74  jmp     loc_14000FE4B
0x14000ff79  mov     esi, 1
0x14000ff7e  jmp     loc_14000FE4B
0x14000ff83  mov     esi, 10h
0x14000ff88  jmp     loc_14000FE4B
0x14000ff8d  mov     eax, 0C001202Ah
0x14000ff92  cmp     ebx, eax
0x14000ff94  jg      short loc_14000FFED
0x14000ff96  jz      short loc_14000FFE3
0x14000ff98  cmp     ebx, 0C0012025h
0x14000ff9e  jz      loc_140010050
0x14000ffa4  cmp     ebx, 0C0012026h
0x14000ffaa  jz      short loc_14000FFD9
0x14000ffac  cmp     ebx, 0C0012027h
0x14000ffb2  jz      loc_14000FE4B
0x14000ffb8  cmp     ebx, 0C0012028h
0x14000ffbe  jz      short loc_14000FFD2
0x14000ffc0  cmp     ebx, 0C0012029h
0x14000ffc6  jnz     short loc_140010009
0x14000ffc8  mov     esi, 200h
0x14000ffcd  jmp     loc_14000FE4B
0x14000ffd2  mov     esi, edx
0x14000ffd4  jmp     loc_14000FE4B
0x14000ffd9  mov     esi, 40h ; '@'
0x14000ffde  jmp     loc_14000FE4B
0x14000ffe3  mov     esi, 400h
0x14000ffe8  jmp     loc_14000FE4B
0x14000ffed  cmp     ebx, 0C001202Bh
0x14000fff3  jz      loc_14000FE46
0x14000fff9  cmp     ebx, 10003h
0x14000ffff  jz      short loc_14001005A
0x140010001  cmp     ebx, 10007h
0x140010007  jz      short loc_140010050
0x140010009  mov     rax, [rdi+58h]
0x14001000d  mov     esi, ecx
0x14001000f  cmp     dword ptr [rax+0ACh], 0Dh
0x140010016  jnz     loc_14000FE4B
0x14001001c  cmp     ebx, 80070079h
0x140010022  jz      short loc_14000FFD9
0x140010024  cmp     ebx, 0C0000241h
0x14001002a  jz      short loc_140010046
0x14001002c  cmp     ebx, 79h ; 'y'
0x14001002f  jz      short loc_14000FFD9
0x140010031  test    ebx, 0FFFF0000h
0x140010037  jnz     short loc_14001003F
0x140010039  or      ebx, 80070000h
0x14001003f  mov     esi, ebx
0x140010041  jmp     loc_14000FE4B
0x140010046  mov     esi, 80000h
0x14001004b  jmp     loc_14000FE4B
0x140010050  mov     esi, 20h ; ' '
0x140010055  jmp     loc_14000FE4B
0x14001005a  mov     esi, 4
0x14001005f  jmp     loc_14000FE4B
0x140010064  mov     dl, [rdi+208h]; NewIrql
0x14001006a  mov     rcx, r14; SpinLock
0x14001006d  call    cs:__imp_KeReleaseSpinLock
0x140010074  nop     dword ptr [rax+rax+00h]
0x140010079  mov     rcx, [rsp+0A8h+var_30]
0x14001007e  xor     rcx, rsp; StackCookie
0x140010081  call    __security_check_cookie
0x140010086  mov     rbx, [rsp+0A8h+arg_10]
0x14001008e  add     rsp, 80h
0x140010095  pop     r14
0x140010097  pop     r12
0x140010099  pop     rdi
0x14001009a  pop     rsi
0x14001009b  pop     rbp
0x14001009c  retn
```
