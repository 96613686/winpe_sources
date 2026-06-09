# SendPacketOnBundle

- ea: `0x140030e70`
- end: `0x14003128f`
- name: `SendPacketOnBundle`
- size: `1055`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140002530`
- `0x140010e00`
- `0x14002dd7c`
- `0x140030940`

## callees

- `0x14000a290`
- `0x14000a2c0`
- `0x140016230`
- `0x140030014`
- `0x140030e70`
- `0x1400312a0`
- `0x1400318c0`
- `0x140035670`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140031019`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031175`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031019`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031175`

## pseudocode

```c
void __fastcall SendPacketOnBundle(char *Entry)
{
  int v2; // eax
  unsigned int v3; // eax
  __int64 v4; // r14
  int v5; // r9d
  char v6; // al
  __int64 v7; // rcx
  __int64 *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rsi
  int v11; // r10d
  char v12; // r8
  __int64 v13; // rbp
  int v14; // eax
  int v15; // edi
  int i; // edi
  int v17; // eax
  KIRQL v18; // dl
  __int64 v19; // rcx
  char *v20; // rsi
  char *v21; // rcx
  __int64 v22; // r8
  char *v23; // rax
  char **v24; // rdx
  KIRQL v25; // dl
  int v26; // edi
  int v27; // [rsp+70h] [rbp+8h] BYREF
  char v28; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v29; // [rsp+80h] [rbp+18h] BYREF
  int v30; // [rsp+88h] [rbp+20h] BYREF

  v28 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xFu, (__int64)WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  v2 = *((_DWORD *)Entry + 4);
  if ( (v2 & 1) != 0 )
  {
    v25 = Entry[1776];
    *((_DWORD *)Entry + 4) = v2 | 2;
    KeReleaseSpinLock((PKSPIN_LOCK)Entry + 221, v25);
    return;
  }
  v3 = v2 | 1;
  v4 = *((_QWORD *)Entry + 38);
  while ( 1 )
  {
    *((_DWORD *)Entry + 4) = v3;
    v5 = *((_DWORD *)Entry + 5);
    v29 = *((_DWORD *)Entry + 78);
    if ( v5 == 2 )
    {
      while ( 1 )
      {
        LOBYTE(v27) = 0;
        do
          v6 = SendFromPPP(Entry, v4, &v28);
        while ( v28 );
        if ( !v6 )
          goto LABEL_27;
        v7 = *((_QWORD *)Entry + 37);
        if ( !v7 )
          goto LABEL_27;
        v8 = (__int64 *)(Entry + 280);
        v9 = *((_DWORD *)Entry + 78) & v29;
        v10 = 0;
        v11 = *((_DWORD *)Entry + 68);
        v12 = 0;
        while ( 1 )
        {
          if ( *(_DWORD *)(v7 + 20) == 3 )
          {
            v10 = v7;
            v12 = 1;
          }
          else
          {
            v9 = ~*(_DWORD *)(v7 + 108) & (unsigned int)v9;
          }
          v7 = *(_QWORD *)v7;
          if ( (__int64 *)v7 == v8 )
            v7 = *v8;
          if ( v12 )
            break;
          if ( !--v11 )
            goto LABEL_17;
        }
        *((_QWORD *)Entry + 37) = v7;
LABEL_17:
        if ( !v10 )
          goto LABEL_27;
        v29 = v9;
        v13 = v10 + 24;
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 24));
        v14 = *((_DWORD *)Entry + 4);
        if ( (v14 & 0x400) != 0 )
          break;
        if ( (_DWORD)v9 )
        {
          v30 = 0;
          v15 = 2;
          do
          {
            SendFromProtocol(Entry, v10, &v30, &v29, &v27);
            --v15;
          }
          while ( v15 );
        }
        for ( i = 0; !i; i = 1 )
        {
          v19 = *((unsigned int *)Entry + 38);
          *((_DWORD *)Entry + 38) = v19 + 1;
          v20 = &Entry[32 * v19 + 112 + 8 * v19];
          if ( !(_DWORD)v19 )
            *((_DWORD *)Entry + 38) = 0;
          if ( *((_DWORD *)v20 + 4) )
          {
LABEL_42:
            v21 = *(char **)v20;
            v22 = *(_QWORD *)(*(_QWORD *)v20 + 40LL);
            while ( v21 != v20 )
            {
              v23 = *(char **)v21;
              if ( *(_BYTE *)(v22 + 201) )
              {
                if ( *((char **)v23 + 1) != v21 || (v24 = (char **)*((_QWORD *)v21 + 1), *v24 != v21) )
                  __fastfail(3u);
                *v24 = v23;
                *((_QWORD *)v23 + 1) = v24;
                --*((_DWORD *)v20 + 4);
                (*(void (**)(void))(v22 + 112))();
                goto LABEL_42;
              }
              v22 = *((_QWORD *)v23 + 5);
              v21 = *(char **)v21;
              ++*((_DWORD *)v20 + 8);
            }
          }
        }
LABEL_24:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(v13 + 8))(v13);
        if ( !v29 || *((_DWORD *)Entry + 5) != 2 )
          goto LABEL_27;
      }
      if ( (v14 & 0x40000) != 0 )
        goto LABEL_65;
      while ( 1 )
      {
        if ( (_BYTE)v27 || !v29 )
          goto LABEL_24;
        v30 = 0;
        v26 = 0;
        while ( (unsigned __int8)SendFromProtocol(Entry, v10, &v30, &v29, &v27) )
        {
          *((_DWORD *)Entry + 4) |= 0x40000u;
          if ( (_BYTE)v27 )
            goto LABEL_64;
          if ( ++v26 > 1 )
            goto LABEL_65;
        }
        if ( !(_BYTE)v27 )
          goto LABEL_65;
LABEL_64:
        if ( v30 == 1 )
          goto LABEL_24;
LABEL_65:
        LOBYTE(v9) = 1;
        if ( (unsigned __int8)SendFromFragQueue(Entry, v9, &v27) )
          *((_DWORD *)Entry + 4) &= ~0x40000u;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x10u,
        (__int64)WPP_8fab404a276b37b5b154f85d9d785092_Traceguids,
        v5);
    }
    FlushBundlePacketQueues(Entry);
LABEL_27:
    v17 = *((_DWORD *)Entry + 4);
    if ( (v17 & 2) == 0 )
      break;
    v3 = v17 & 0xFFFFFFFD;
  }
  v18 = Entry[1776];
  *((_DWORD *)Entry + 4) = v17 & 0xFFFFFFFE;
  KeReleaseSpinLock((PKSPIN_LOCK)Entry + 221, v18);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x11u,
      (__int64)WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
}

```

## disassembly

```asm
0x140030e70  push    rbx
0x140030e72  push    r12
0x140030e74  sub     rsp, 58h
0x140030e78  mov     rbx, rcx
0x140030e7b  mov     [rsp+68h+arg_8], 0
0x140030e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e87  lea     r12, WPP_GLOBAL_Control
0x140030e8e  cmp     rcx, r12
0x140030e91  jz      short loc_140030E9E
0x140030e93  mov     eax, [rcx+2Ch]
0x140030e96  test    al, 8
0x140030e98  jnz     loc_14003113D
0x140030e9e  mov     eax, [rbx+10h]
0x140030ea1  test    al, 1
0x140030ea3  jnz     loc_140031161
0x140030ea9  mov     [rsp+68h+var_18], rbp
0x140030eae  or      eax, 1
0x140030eb1  mov     [rsp+68h+var_20], rsi
0x140030eb6  mov     [rsp+68h+var_28], rdi
0x140030ebb  mov     [rsp+68h+var_30], r14
0x140030ec0  mov     r14, [rbx+130h]
0x140030ec7  mov     [rsp+68h+var_38], r15
0x140030ecc  xor     r15d, r15d
0x140030ecf  mov     [rbx+10h], eax
0x140030ed2  mov     r9d, [rbx+14h]
0x140030ed6  mov     eax, [rbx+138h]
0x140030edc  mov     [rsp+68h+arg_10], eax
0x140030ee3  cmp     r9d, 2
0x140030ee7  jnz     loc_1400310BF
0x140030eed  mov     byte ptr [rsp+68h+arg_0], r15b
0x140030ef2  lea     r8, [rsp+68h+arg_8]
0x140030ef7  mov     rdx, r14
0x140030efa  mov     rcx, rbx
0x140030efd  call    SendFromPPP
0x140030f02  cmp     [rsp+68h+arg_8], r15b
0x140030f07  jnz     short loc_140030EF2
0x140030f09  test    al, al
0x140030f0b  jz      loc_140030FFA
0x140030f11  mov     rcx, [rbx+128h]
0x140030f18  test    rcx, rcx
0x140030f1b  jz      loc_140030FFA
0x140030f21  mov     edx, [rsp+68h+arg_10]
0x140030f28  lea     r9, [rbx+118h]
0x140030f2f  and     edx, [rbx+138h]
0x140030f35  mov     rsi, r15
0x140030f38  mov     r10d, [rbx+110h]
0x140030f3f  xor     r8b, r8b
0x140030f42  cmp     dword ptr [rcx+14h], 3
0x140030f46  jnz     loc_1400310B3
0x140030f4c  mov     rsi, rcx
0x140030f4f  mov     r8b, 1
0x140030f52  mov     rcx, [rcx]
0x140030f55  cmp     rcx, r9
0x140030f58  jnz     short loc_140030F5D
0x140030f5a  mov     rcx, [r9]
0x140030f5d  test    r8b, r8b
0x140030f60  jz      loc_1400310A4
0x140030f66  mov     [rbx+128h], rcx
0x140030f6d  test    rsi, rsi
0x140030f70  jz      loc_140030FFA
0x140030f76  mov     [rsp+68h+arg_10], edx
0x140030f7d  lea     rbp, [rsi+18h]
0x140030f81  lock inc dword ptr [rbp+0]
0x140030f85  mov     eax, [rbx+10h]
0x140030f88  bt      eax, 0Ah
0x140030f8c  jb      loc_1400311B5
0x140030f92  test    edx, edx
0x140030f94  jz      short loc_140030FCD
0x140030f96  mov     [rsp+68h+arg_18], r15d
0x140030f9e  mov     edi, 2
0x140030fa3  lea     rax, [rsp+68h+arg_0]
0x140030fa8  mov     rdx, rsi
0x140030fab  lea     r9, [rsp+68h+arg_10]
0x140030fb3  mov     qword ptr [rsp+68h+var_48], rax; int
0x140030fb8  lea     r8, [rsp+68h+arg_18]
0x140030fc0  mov     rcx, rbx; Entry
0x140030fc3  call    SendFromProtocol
0x140030fc8  sub     edi, 1
0x140030fcb  jnz     short loc_140030FA3
0x140030fcd  mov     edi, r15d
0x140030fd0  cmp     edi, 1
0x140030fd3  jb      loc_14003105E
0x140030fd9  mov     eax, 0FFFFFFFFh
0x140030fde  lock xadd [rbp+0], eax
0x140030fe3  cmp     eax, 1
0x140030fe6  jz      loc_1400310DC
0x140030fec  cmp     [rsp+68h+arg_10], r15d
0x140030ff4  jnz     loc_140031095
0x140030ffa  mov     eax, [rbx+10h]
0x140030ffd  test    al, 2
0x140030fff  jnz     loc_14003125C
0x140031005  movzx   edx, byte ptr [rbx+6F0h]; NewIrql
0x14003100c  lea     rcx, [rbx+6E8h]; SpinLock
0x140031013  and     eax, 0FFFFFFFEh
0x140031016  mov     [rbx+10h], eax
0x140031019  call    cs:__imp_KeReleaseSpinLock
0x140031020  nop     dword ptr [rax+rax+00h]
0x140031025  mov     rcx, cs:WPP_GLOBAL_Control
0x14003102c  cmp     rcx, r12
0x14003102f  jz      short loc_14003103C
0x140031031  mov     eax, [rcx+2Ch]
0x140031034  test    al, 8
0x140031036  jnz     loc_14003126B
0x14003103c  mov     r14, [rsp+68h+var_30]
0x140031041  mov     rdi, [rsp+68h+var_28]
0x140031046  mov     rsi, [rsp+68h+var_20]
0x14003104b  mov     rbp, [rsp+68h+var_18]
0x140031050  mov     r15, [rsp+68h+var_38]
0x140031055  add     rsp, 58h
0x140031059  pop     r12
0x14003105b  pop     rbx
0x14003105c  retn
0x14003105e  mov     ecx, [rbx+98h]
0x140031064  lea     eax, [rcx+1]
0x140031067  lea     rsi, ds:0Eh[rcx*4]
0x14003106f  mov     [rbx+98h], eax
0x140031075  add     rsi, rcx
0x140031078  lea     rsi, [rbx+rsi*8]
0x14003107c  cmp     eax, 1
0x14003107f  jnz     short loc_140031088
0x140031081  mov     [rbx+98h], r15d
0x140031088  cmp     [rsi+10h], r15d
0x14003108c  jnz     short loc_1400310ED
0x14003108e  inc     edi
0x140031090  jmp     loc_140030FD0
0x140031095  cmp     dword ptr [rbx+14h], 2
0x140031099  jz      loc_140030EED
0x14003109f  jmp     loc_140030FFA
0x1400310a4  add     r10d, 0FFFFFFFFh
0x1400310a8  jz      loc_140030F6D
0x1400310ae  jmp     loc_140030F42
0x1400310b3  mov     eax, [rcx+6Ch]
0x1400310b6  not     eax
0x1400310b8  and     edx, eax
0x1400310ba  jmp     loc_140030F52
0x1400310bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400310c6  cmp     rcx, r12
0x1400310c9  jnz     loc_140031186
0x1400310cf  mov     rcx, rbx
0x1400310d2  call    FlushBundlePacketQueues
0x1400310d7  jmp     loc_140030FFA
0x1400310dc  mov     rax, [rbp+8]
0x1400310e0  mov     rcx, rbp
0x1400310e3  call    _guard_dispatch_icall
0x1400310e8  jmp     loc_140030FEC
0x1400310ed  mov     rcx, [rsi]
0x1400310f0  mov     r8, [rcx+28h]
0x1400310f4  cmp     rcx, rsi
0x1400310f7  jz      short loc_14003108E
0x1400310f9  mov     rax, [rcx]
0x1400310fc  cmp     [r8+0C9h], r15b
0x140031103  jnz     short loc_140031111
0x140031105  mov     r8, [rax+28h]
0x140031109  mov     rcx, rax
0x14003110c  inc     dword ptr [rsi+20h]
0x14003110f  jmp     short loc_1400310F4
0x140031111  cmp     [rax+8], rcx
0x140031115  jnz     loc_140031264
0x14003111b  mov     rdx, [rcx+8]
0x14003111f  cmp     [rdx], rcx
0x140031122  jnz     loc_140031264
0x140031128  mov     [rdx], rax
0x14003112b  mov     [rax+8], rdx
0x14003112f  dec     dword ptr [rsi+10h]
0x140031132  mov     rax, [r8+70h]
0x140031136  call    _guard_dispatch_icall
0x14003113b  jmp     short loc_1400310ED
0x14003113d  cmp     byte ptr [rcx+29h], 5
0x140031141  jb      loc_140030E9E
0x140031147  mov     rcx, [rcx+18h]
0x14003114b  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140031152  mov     edx, 0Fh
0x140031157  call    WPP_SF_
0x14003115c  jmp     loc_140030E9E
0x140031161  movzx   edx, byte ptr [rbx+6F0h]; NewIrql
0x140031168  lea     rcx, [rbx+6E8h]; SpinLock
0x14003116f  or      eax, 2
0x140031172  mov     [rbx+10h], eax
0x140031175  call    cs:__imp_KeReleaseSpinLock
0x14003117c  nop     dword ptr [rax+rax+00h]
0x140031181  jmp     loc_140031055
0x140031186  mov     eax, [rcx+2Ch]
0x140031189  test    al, 8
0x14003118b  jz      loc_1400310CF
0x140031191  cmp     byte ptr [rcx+29h], 5
0x140031195  jb      loc_1400310CF
0x14003119b  mov     rcx, [rcx+18h]
0x14003119f  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x1400311a6  mov     edx, 10h
0x1400311ab  call    WPP_SF_d
0x1400311b0  jmp     loc_1400310CF
0x1400311b5  bt      eax, 12h
0x1400311b9  jnb     short loc_1400311C7
0x1400311bb  jmp     loc_140031240
0x1400311c0  and     dword ptr [rbx+10h], 0FFFBFFFFh
0x1400311c7  cmp     byte ptr [rsp+68h+arg_0], r15b
0x1400311cc  jnz     loc_140030FD9
0x1400311d2  cmp     [rsp+68h+arg_10], r15d
0x1400311da  jz      loc_140030FD9
0x1400311e0  mov     [rsp+68h+arg_18], r15d
0x1400311e8  mov     edi, r15d
0x1400311eb  lea     rax, [rsp+68h+arg_0]
0x1400311f0  mov     rdx, rsi
0x1400311f3  lea     r9, [rsp+68h+arg_10]
0x1400311fb  mov     qword ptr [rsp+68h+var_48], rax; int
0x140031200  lea     r8, [rsp+68h+arg_18]
0x140031208  mov     rcx, rbx; Entry
0x14003120b  call    SendFromProtocol
0x140031210  test    al, al
0x140031212  jz      short loc_14003122B
0x140031214  or      dword ptr [rbx+10h], 40000h
0x14003121b  cmp     byte ptr [rsp+68h+arg_0], r15b
0x140031220  jnz     short loc_140031232
0x140031222  inc     edi
0x140031224  cmp     edi, 1
0x140031227  jle     short loc_1400311EB
0x140031229  jmp     short loc_140031240
0x14003122b  cmp     byte ptr [rsp+68h+arg_0], r15b
0x140031230  jz      short loc_140031240
0x140031232  cmp     [rsp+68h+arg_18], 1
0x14003123a  jz      loc_140030FD9
0x140031240  lea     r8, [rsp+68h+arg_0]
0x140031245  mov     dl, 1
0x140031247  mov     rcx, rbx
0x14003124a  call    SendFromFragQueue
0x14003124f  test    al, al
0x140031251  jz      loc_1400311C7
0x140031257  jmp     loc_1400311C0
0x14003125c  and     eax, 0FFFFFFFDh
0x14003125f  jmp     loc_140030ECF
0x140031264  mov     ecx, 3
0x140031269  int     29h; Win8: RtlFailFast(ecx)
0x14003126b  cmp     byte ptr [rcx+29h], 5
0x14003126f  jb      loc_14003103C
0x140031275  mov     rcx, [rcx+18h]
0x140031279  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140031280  mov     edx, 11h
0x140031285  call    WPP_SF_
0x14003128a  jmp     loc_14003103C
```
