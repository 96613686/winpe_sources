# CWriteEngineSectionResources::WaitForNextWriteBuffer(ulong *)

- ea: `0x180008760`
- end: `0x18000894c`
- name: `?WaitForNextWriteBuffer@CWriteEngineSectionResources@@QEAAJPEAK@Z`
- size: `492`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008510`

## callees

- `0x180008760`
- `0x180014134`
- `0x180016778`
- `0x180049880`

## import_xrefs

- `USER32!MsgWaitForMultipleObjects` at `0x1800087c7`
- `USER32!MsgWaitForMultipleObjects` at `0x1800087c7`

## pseudocode

```c
__int64 __fastcall CWriteEngineSectionResources::WaitForNextWriteBuffer(HANDLE *this, unsigned int *a2)
{
  unsigned int v2; // ebx
  HANDLE v5; // rax
  __int64 v6; // rcx
  DWORD v7; // eax
  _QWORD *v8; // rcx
  __int64 v10; // rdx
  HANDLE v11[3]; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  if ( a2 )
  {
    *a2 = -2097152;
    v11[0] = this[2];
    v5 = this[7];
    v6 = *((unsigned int *)this + 17);
    v11[1] = v5;
    v11[2] = *((HANDLE *)this[6] + v6);
    v7 = MsgWaitForMultipleObjects(3u, v11, 0, 0xFFFFFFFF, 0);
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        v2 = -1062600702;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
        {
          v10 = 29;
          goto LABEL_16;
        }
      }
      else if ( v7 == 2 )
      {
        *a2 = *((_DWORD *)this + 17);
        *((_DWORD *)this + 17) = (unsigned int)(*((_DWORD *)this + 17) + 1) % *((_DWORD *)this + 8);
      }
      else
      {
        v2 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, v7, v7);
        }
      }
    }
    else
    {
      v2 = -1062600702;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
      {
        v10 = 28;
LABEL_16:
        WPP_SF_(v8[27], v10, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 27, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
    }
    return (unsigned int)-2147467261;
  }
  return v2;
}

```

## disassembly

```asm
0x180008760  mov     r11, rsp
0x180008763  mov     [r11+18h], rbx
0x180008767  mov     [r11+20h], rsi
0x18000876b  push    rdi
0x18000876c  sub     rsp, 50h
0x180008770  mov     rax, cs:__security_cookie
0x180008777  xor     rax, rsp
0x18000877a  mov     [rsp+58h+var_10], rax
0x18000877f  xor     ebx, ebx
0x180008781  mov     rsi, rdx
0x180008784  mov     rdi, rcx
0x180008787  test    rdx, rdx
0x18000878a  jz      loc_180008837
0x180008790  mov     dword ptr [rdx], 0FFE00000h
0x180008796  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000879a  mov     rax, [rcx+10h]
0x18000879e  lea     rdx, [r11-28h]; pHandles
0x1800087a2  mov     [r11-28h], rax
0x1800087a6  xor     r8d, r8d; fWaitAll
0x1800087a9  mov     rax, [rcx+38h]
0x1800087ad  mov     ecx, [rcx+44h]
0x1800087b0  mov     [r11-20h], rax
0x1800087b4  mov     rax, [rdi+30h]
0x1800087b8  mov     [rsp+58h+dwWakeMask], ebx; dwWakeMask
0x1800087bc  mov     rcx, [rax+rcx*8]
0x1800087c0  mov     [r11-18h], rcx
0x1800087c4  lea     ecx, [rbx+3]; nCount
0x1800087c7  call    cs:__imp_MsgWaitForMultipleObjects
0x1800087cd  mov     r9d, eax
0x1800087d0  test    eax, eax
0x1800087d2  jnz     short loc_18000880F
0x1800087d4  mov     ebx, 0C0AA0002h
0x1800087d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087e0  lea     rax, WPP_GLOBAL_Control
0x1800087e7  cmp     rcx, rax
0x1800087ea  jnz     loc_18000887E
0x1800087f0  mov     eax, ebx
0x1800087f2  mov     rcx, [rsp+58h+var_10]
0x1800087f7  xor     rcx, rsp; StackCookie
0x1800087fa  call    __security_check_cookie
0x1800087ff  mov     rbx, [rsp+58h+arg_10]
0x180008804  mov     rsi, [rsp+58h+arg_18]
0x180008809  add     rsp, 50h
0x18000880d  pop     rdi
0x18000880e  retn
0x18000880f  cmp     r9d, 1
0x180008813  jz      loc_1800088BC
0x180008819  cmp     r9d, 2
0x18000881d  jnz     loc_1800088F4
0x180008823  mov     ecx, [rdi+44h]
0x180008826  xor     edx, edx
0x180008828  mov     [rsi], ecx
0x18000882a  mov     eax, [rdi+44h]
0x18000882d  inc     eax
0x18000882f  div     dword ptr [rdi+20h]
0x180008832  mov     [rdi+44h], edx
0x180008835  jmp     short loc_1800087F0
0x180008837  mov     rcx, cs:WPP_GLOBAL_Control
0x18000883e  lea     rax, WPP_GLOBAL_Control
0x180008845  cmp     rcx, rax
0x180008848  jz      short loc_180008874
0x18000884a  test    byte ptr [rcx+0E4h], 4
0x180008851  jz      short loc_180008874
0x180008853  cmp     byte ptr [rcx+0E1h], 3
0x18000885a  jb      short loc_180008874
0x18000885c  mov     rcx, [rcx+0D8h]
0x180008863  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x18000886a  mov     edx, 1Bh
0x18000886f  call    WPP_SF_
0x180008874  mov     ebx, 80004003h
0x180008879  jmp     loc_1800087F0
0x18000887e  test    byte ptr [rcx+0E4h], 4
0x180008885  jz      loc_1800087F0
0x18000888b  cmp     byte ptr [rcx+0E1h], 2
0x180008892  jb      loc_1800087F0
0x180008898  mov     edx, 1Ch
0x18000889d  jmp     short loc_1800088A4
0x18000889f  mov     edx, 1Dh
0x1800088a4  mov     rcx, [rcx+0D8h]
0x1800088ab  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x1800088b2  call    WPP_SF_
0x1800088b7  jmp     loc_1800087F0
0x1800088bc  mov     ebx, 0C0AA0002h
0x1800088c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088c8  lea     rax, WPP_GLOBAL_Control
0x1800088cf  cmp     rcx, rax
0x1800088d2  jz      loc_1800087F0
0x1800088d8  test    byte ptr [rcx+0E4h], 4
0x1800088df  jz      loc_1800087F0
0x1800088e5  cmp     byte ptr [rcx+0E1h], 2
0x1800088ec  jb      loc_1800087F0
0x1800088f2  jmp     short loc_18000889F
0x1800088f4  mov     ebx, 80004005h
0x1800088f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008900  lea     rax, WPP_GLOBAL_Control
0x180008907  cmp     rcx, rax
0x18000890a  jz      loc_1800087F0
0x180008910  test    byte ptr [rcx+0E4h], 4
0x180008917  jz      loc_1800087F0
0x18000891d  cmp     byte ptr [rcx+0E1h], 2
0x180008924  jb      loc_1800087F0
0x18000892a  mov     rcx, [rcx+0D8h]
0x180008931  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x180008938  mov     edx, 1Eh
0x18000893d  mov     [rsp+58h+dwWakeMask], r9d
0x180008942  call    WPP_SF_Dd
0x180008947  jmp     loc_1800087F0
```
