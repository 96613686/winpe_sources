# GraphicSetAudio

- ea: `0x180005634`
- end: `0x1800057fc`
- name: `GraphicSetAudio`
- size: `456`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180001dfc`
- `0x1800023d4`
- `0x18000310c`
- `0x180005634`
- `0x180007010`

## import_xrefs

- `QUARTZ!AmpFactorToDB` at `0x1800056ba`
- `QUARTZ!AmpFactorToDB` at `0x1800056ba`

## pseudocode

```c
__int64 __fastcall GraphicSetAudio(struct _MCIGRAPHIC *a1, unsigned int a2, __int64 a3)
{
  int v5; // ecx
  int v6; // ebp
  unsigned int v7; // esi
  int v8; // eax
  int v9; // eax
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // ecx

  v5 = *((_DWORD *)a1 + 21);
  if ( !v5 )
    return 274;
  v6 = a2 & 0x800000;
  if ( (a2 & 0x800000) != 0 )
  {
    if ( *(_DWORD *)(a3 + 8) == 16386 )
    {
      if ( (a2 & 0x1000000) != 0 )
      {
        if ( (a2 & 0x1E0000) == 0 )
        {
          if ( *(_DWORD *)(a3 + 12) <= 0x3E8u )
          {
            if ( (a2 & 0x20) == 0 )
            {
              if ( *((_QWORD *)a1 + 23) )
              {
                v7 = 0xFFFF * *(_DWORD *)(a3 + 12) / 0x3E8u;
                v8 = AmpFactorToDB(v7);
                if ( (a2 & 0x200000) == 0 )
                {
                  *((_DWORD *)a1 + 59) = v7;
                  *((_DWORD *)a1 + 60) = v8;
                }
                if ( (a2 & 0x400000) == 0 )
                {
                  *((_DWORD *)a1 + 56) = v7;
                  *((_DWORD *)a1 + 57) = v8;
                }
                ActuallySetVolume(a1);
              }
              goto LABEL_35;
            }
            return 0;
          }
          return 282;
        }
        return 274;
      }
    }
    else
    {
      v9 = a2 & 0x1000000;
      if ( *(_DWORD *)(a3 + 8) == 16387 )
      {
        if ( v9 )
        {
          if ( (a2 & 0x7E0000) == 0 )
          {
            if ( *(_DWORD *)(a3 + 12) <= (unsigned int)v5 && *(_DWORD *)(a3 + 12) )
            {
              if ( (a2 & 0x20) == 0 )
              {
                if ( v5 > 1 )
                  DeviceSetStream(a1, *(unsigned __int16 *)(a3 + 12), &MEDIATYPE_Audio);
                goto LABEL_35;
              }
              return 0;
            }
            return 282;
          }
          return 274;
        }
      }
      else if ( *(_DWORD *)(a3 + 8) == 16388 && v9 )
      {
        v11 = *(_DWORD *)(a3 + 12);
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( v12 != 1 )
              goto LABEL_35;
            v13 = 2;
          }
          else
          {
            v13 = 1;
          }
        }
        else
        {
          v13 = 0;
        }
        v14 = *((_QWORD *)a1 + 67);
        if ( v14 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 112LL))(v14, v13);
        goto LABEL_35;
      }
    }
  }
  if ( (a2 & 0x19E0000) != 0 )
    return 274;
LABEL_35:
  v15 = 0;
  if ( (((a2 & 0x6000) - 0x2000) & 0xFFFFDFFF) != 0 )
  {
    if ( (a2 & 0x6000) == 0x6000 )
    {
      return 284;
    }
    else if ( !v6 )
    {
      return 273;
    }
  }
  else if ( (a2 & 0x20) == 0 )
  {
    return DeviceMute(a1, a2);
  }
  return v15;
}

```

## disassembly

```asm
0x180005634  push    rbx
0x180005636  push    rbp
0x180005637  push    rsi
0x180005638  push    rdi
0x180005639  sub     rsp, 28h
0x18000563d  mov     rdi, rcx
0x180005640  mov     ebx, edx
0x180005642  mov     ecx, [rcx+54h]
0x180005645  test    ecx, ecx
0x180005647  jz      loc_1800057EE
0x18000564d  mov     ebp, edx
0x18000564f  and     ebp, 800000h
0x180005655  jz      loc_1800057A0
0x18000565b  cmp     dword ptr [r8+8], 4002h
0x180005663  jnz     loc_1800056F1
0x180005669  bt      edx, 18h
0x18000566d  jnb     loc_1800057A0
0x180005673  test    edx, 1E0000h
0x180005679  jnz     loc_1800057EE
0x18000567f  cmp     dword ptr [r8+0Ch], 3E8h
0x180005687  ja      loc_18000574E
0x18000568d  test    bl, 20h
0x180005690  jnz     loc_180005728
0x180005696  cmp     qword ptr [rdi+0B8h], 0
0x18000569e  jz      loc_1800057A8
0x1800056a4  imul    ecx, [r8+0Ch], 0FFFFh
0x1800056ac  mov     eax, 10624DD3h
0x1800056b1  mul     ecx
0x1800056b3  mov     esi, edx
0x1800056b5  shr     esi, 6
0x1800056b8  mov     ecx, esi
0x1800056ba  call    cs:__imp_AmpFactorToDB
0x1800056c0  bt      ebx, 15h
0x1800056c4  jb      short loc_1800056D2
0x1800056c6  mov     [rdi+0ECh], esi
0x1800056cc  mov     [rdi+0F0h], eax
0x1800056d2  bt      ebx, 16h
0x1800056d6  jb      short loc_1800056E4
0x1800056d8  mov     [rdi+0E0h], esi
0x1800056de  mov     [rdi+0E4h], eax
0x1800056e4  mov     rcx, rdi; struct _MCIGRAPHIC *
0x1800056e7  call    ?ActuallySetVolume@@YAJPEAU_MCIGRAPHIC@@@Z; ActuallySetVolume(_MCIGRAPHIC *)
0x1800056ec  jmp     loc_1800057A8
0x1800056f1  mov     eax, ebx
0x1800056f3  and     eax, 1000000h
0x1800056f8  cmp     dword ptr [r8+8], 4003h
0x180005700  jnz     short loc_180005758
0x180005702  test    eax, eax
0x180005704  jz      loc_1800057A0
0x18000570a  test    ebx, 7E0000h
0x180005710  jnz     loc_1800057EE
0x180005716  cmp     [r8+0Ch], ecx
0x18000571a  ja      short loc_18000574E
0x18000571c  cmp     dword ptr [r8+0Ch], 0
0x180005721  jz      short loc_18000574E
0x180005723  test    bl, 20h
0x180005726  jz      short loc_18000572F
0x180005728  xor     eax, eax
0x18000572a  jmp     loc_1800057F3
0x18000572f  mov     edx, 1
0x180005734  cmp     ecx, edx
0x180005736  jle     short loc_1800057A8
0x180005738  movzx   edx, word ptr [r8+0Ch]; unsigned int
0x18000573d  mov     rcx, rdi; struct _MCIGRAPHIC *
0x180005740  lea     r8, MEDIATYPE_Audio; struct _GUID *
0x180005747  call    ?DeviceSetStream@@YAJPEAU_MCIGRAPHIC@@IPEBU_GUID@@@Z; DeviceSetStream(_MCIGRAPHIC *,uint,_GUID const *)
0x18000574c  jmp     short loc_1800057A8
0x18000574e  mov     eax, 11Ah
0x180005753  jmp     loc_1800057F3
0x180005758  cmp     dword ptr [r8+8], 4004h
0x180005760  jnz     short loc_1800057A0
0x180005762  test    eax, eax
0x180005764  jz      short loc_1800057A0
0x180005766  mov     ecx, [r8+0Ch]
0x18000576a  test    ecx, ecx
0x18000576c  jz      short loc_180005784
0x18000576e  sub     ecx, 1
0x180005771  jz      short loc_18000577D
0x180005773  cmp     ecx, 1
0x180005776  jnz     short loc_1800057A8
0x180005778  lea     edx, [rcx+1]
0x18000577b  jmp     short loc_180005786
0x18000577d  mov     edx, 1
0x180005782  jmp     short loc_180005786
0x180005784  xor     edx, edx
0x180005786  mov     rcx, [rdi+218h]
0x18000578d  test    rcx, rcx
0x180005790  jz      short loc_1800057A8
0x180005792  mov     rax, [rcx]
0x180005795  mov     rax, [rax+70h]
0x180005799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000579e  jmp     short loc_1800057A8
0x1800057a0  test    ebx, 19E0000h
0x1800057a6  jnz     short loc_1800057EE
0x1800057a8  mov     edx, ebx
0x1800057aa  mov     r8d, 6000h
0x1800057b0  and     edx, r8d
0x1800057b3  xor     ecx, ecx
0x1800057b5  lea     eax, [rdx-2000h]
0x1800057bb  test    eax, 0FFFFDFFFh
0x1800057c0  jz      short loc_1800057D9
0x1800057c2  cmp     edx, r8d
0x1800057c5  jz      short loc_1800057D2
0x1800057c7  test    ebp, ebp
0x1800057c9  jnz     short loc_1800057EA
0x1800057cb  mov     ecx, 111h
0x1800057d0  jmp     short loc_1800057EA
0x1800057d2  mov     ecx, 11Ch
0x1800057d7  jmp     short loc_1800057EA
0x1800057d9  test    bl, 20h
0x1800057dc  jnz     short loc_1800057EA
0x1800057de  mov     edx, ebx; unsigned int
0x1800057e0  mov     rcx, rdi; struct _MCIGRAPHIC *
0x1800057e3  call    ?DeviceMute@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceMute(_MCIGRAPHIC *,ulong)
0x1800057e8  mov     ecx, eax
0x1800057ea  mov     eax, ecx
0x1800057ec  jmp     short loc_1800057F3
0x1800057ee  mov     eax, 112h
0x1800057f3  add     rsp, 28h
0x1800057f7  pop     rdi
0x1800057f8  pop     rsi
0x1800057f9  pop     rbp
0x1800057fa  pop     rbx
0x1800057fb  retn
```
