# HidServUpdate

- ea: `0x180003594`
- end: `0x180003ff2`
- name: `HidServUpdate`
- size: `2654`
- prototype: `int __fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002e40`

## callees

- `0x1800025e0`
- `0x180002838`
- `0x180003594`
- `0x180004650`
- `0x180004884`
- `0x180004920`
- `0x180005038`
- `0x1800050e4`
- `0x18000841e`
- `0x180008450`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180003e95`
- `ntdll!RtlPublishWnfStateData` at `0x180003e95`
- `KERNEL32!WaitForSingleObject` at `0x18000376e`
- `KERNEL32!WaitForSingleObject` at `0x180003818`
- `KERNEL32!WaitForSingleObject` at `0x180003889`
- `KERNEL32!WaitForSingleObject` at `0x1800038fa`
- `KERNEL32!WaitForSingleObject` at `0x180003b81`
- `KERNEL32!WaitForSingleObject` at `0x180003bf2`
- `KERNEL32!WaitForSingleObject` at `0x180003c63`
- `KERNEL32!WaitForSingleObject` at `0x180003cd9`
- `KERNEL32!WaitForSingleObject` at `0x180003d56`
- `KERNEL32!WaitForSingleObject` at `0x180003dda`
- `KERNEL32!WaitForSingleObject` at `0x18000376e`
- `KERNEL32!WaitForSingleObject` at `0x180003818`
- `KERNEL32!WaitForSingleObject` at `0x180003889`
- `KERNEL32!WaitForSingleObject` at `0x1800038fa`
- `KERNEL32!WaitForSingleObject` at `0x180003b81`
- `KERNEL32!WaitForSingleObject` at `0x180003bf2`
- `KERNEL32!WaitForSingleObject` at `0x180003c63`
- `KERNEL32!WaitForSingleObject` at `0x180003cd9`
- `KERNEL32!WaitForSingleObject` at `0x180003d56`
- `KERNEL32!WaitForSingleObject` at `0x180003dda`
- `KERNEL32!ReleaseMutex` at `0x180003db8`
- `KERNEL32!ReleaseMutex` at `0x180003db8`
- `USER32!KillTimer` at `0x1800037c3`
- `USER32!KillTimer` at `0x18000386d`
- `USER32!KillTimer` at `0x1800038de`
- `USER32!KillTimer` at `0x18000394f`
- `USER32!KillTimer` at `0x180003bd6`
- `USER32!KillTimer` at `0x180003c47`
- `USER32!KillTimer` at `0x180003cb8`
- `USER32!KillTimer` at `0x180003d2b`
- `USER32!KillTimer` at `0x180003da4`
- `USER32!KillTimer` at `0x180003e28`
- `USER32!KillTimer` at `0x1800037c3`
- `USER32!KillTimer` at `0x18000386d`
- `USER32!KillTimer` at `0x1800038de`
- `USER32!KillTimer` at `0x18000394f`
- `USER32!KillTimer` at `0x180003bd6`
- `USER32!KillTimer` at `0x180003c47`
- `USER32!KillTimer` at `0x180003cb8`
- `USER32!KillTimer` at `0x180003d2b`
- `USER32!KillTimer` at `0x180003da4`
- `USER32!KillTimer` at `0x180003e28`
- `USER32!SetTimer` at `0x1800037a5`
- `USER32!SetTimer` at `0x18000384f`
- `USER32!SetTimer` at `0x1800038c0`
- `USER32!SetTimer` at `0x180003931`
- `USER32!SetTimer` at `0x180003bb8`
- `USER32!SetTimer` at `0x180003c29`
- `USER32!SetTimer` at `0x180003c9a`
- `USER32!SetTimer` at `0x180003d0f`
- `USER32!SetTimer` at `0x180003d89`
- `USER32!SetTimer` at `0x180003e0d`
- `USER32!SetTimer` at `0x1800037a5`
- `USER32!SetTimer` at `0x18000384f`
- `USER32!SetTimer` at `0x1800038c0`
- `USER32!SetTimer` at `0x180003931`
- `USER32!SetTimer` at `0x180003bb8`
- `USER32!SetTimer` at `0x180003c29`
- `USER32!SetTimer` at `0x180003c9a`
- `USER32!SetTimer` at `0x180003d0f`
- `USER32!SetTimer` at `0x180003d89`
- `USER32!SetTimer` at `0x180003e0d`

## pseudocode

```c
int __fastcall HidServUpdate(unsigned int a1, unsigned int a2)
{
  unsigned int v2; // ebp
  int result; // eax
  unsigned int v4; // r14d
  unsigned __int16 v5; // si
  unsigned __int16 v6; // bx
  unsigned __int16 v7; // di
  _QWORD *v8; // rcx
  _UNKNOWN **v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int16 v13; // di
  __int64 v14; // rcx
  UINT_PTR v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // [rsp+40h] [rbp-128h] BYREF
  _BYTE v18[232]; // [rsp+48h] [rbp-120h] BYREF

  v2 = HIWORD(a1);
  result = 0x7FFF;
  v4 = HIWORD(a2);
  v5 = a1 & 0x7FFF;
  v6 = a2;
  v7 = a1;
  v8 = WPP_GLOBAL_Control;
  v9 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    result = WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_GLOBAL_Control, v2, v4, v5, (__int16)a2);
    v8 = WPP_GLOBAL_Control;
    v9 = &WPP_GLOBAL_Control;
  }
  if ( (_WORD)v2 != 1 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      return WPP_SF_DD(v8[2], 35, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v2, v5);
    return result;
  }
  v10 = v4;
  v11 = v4;
  if ( !v4 )
    goto LABEL_21;
  v11 = v4 - 1;
  if ( v4 != 1 )
  {
    if ( v4 != 12 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      {
        v12 = 34;
        return WPP_SF_D(v8[2], v12, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v10);
      }
      return result;
    }
LABEL_21:
    v13 = v7 >> 15;
    result = 231;
    v10 = v5;
    if ( v5 <= 0xE7u )
    {
      if ( v5 == 231 )
        return result;
      result = 209;
      if ( v5 > 0xD1u )
      {
        result = 215;
        if ( v5 <= 0xD7u )
        {
          switch ( v5 )
          {
            case 0xD7u:
              if ( !v6 )
                return result;
              v14 = 62;
              break;
            case 0xD2u:
              if ( !v6 )
                return result;
              v14 = 57;
              break;
            case 0xD3u:
              if ( !v6 )
                return result;
              v14 = 58;
              break;
            case 0xD4u:
              if ( !v6 )
                return result;
              v14 = 59;
              break;
            case 0xD5u:
              if ( !v6 )
                return result;
              v14 = 60;
              break;
            default:
              if ( !v6 )
                return result;
              v14 = 61;
              break;
          }
          return SendAppCommand(v14);
        }
        if ( v5 == 224 )
        {
          if ( (__int16)v6 <= 0 )
          {
            if ( (v6 & 0x8000u) == 0 )
              return result;
            v14 = 9;
          }
          else
          {
            v14 = 10;
          }
          return SendAppCommand(v14);
        }
        if ( v5 != 226 )
        {
          switch ( v5 )
          {
            case 0xE3u:
              if ( (__int16)v6 <= 0 )
              {
                if ( (v6 & 0x8000u) == 0 )
                  return result;
                v14 = 19;
              }
              else
              {
                v14 = 21;
              }
              break;
            case 0xE4u:
              if ( (__int16)v6 <= 0 )
              {
                if ( (v6 & 0x8000u) == 0 )
                  return result;
                v14 = 22;
              }
              else
              {
                v14 = 23;
              }
              break;
            case 0xE5u:
              if ( !v6 )
                return result;
              v14 = 20;
              break;
            default:
              goto LABEL_181;
          }
          return SendAppCommand(v14);
        }
        if ( (_BYTE)v13 )
        {
          if ( !v6 )
            return result;
          v14 = 8;
          return SendAppCommand(v14);
        }
        LOBYTE(v8) = -83;
        return SendVK(v8, v6);
      }
      if ( v5 == 209 )
      {
        if ( !v6 )
          return result;
        v14 = 56;
        return SendAppCommand(v14);
      }
      if ( v5 <= 0xB4u )
      {
        switch ( v5 )
        {
          case 0xB4u:
            WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
            if ( v6 )
            {
              if ( !qword_18000D898 )
              {
                SendAppCommand(50);
                qword_18000D898 = SetTimer(hWndHidServ, 0x16u, INITIAL_WAIT, 0);
              }
            }
            else
            {
              KillTimer(hWndHidServ, 0x16u);
              qword_18000D898 = 0;
            }
            return ReleaseMutex(hMutexOOC);
          case 0x9Cu:
            WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
            if ( v6 )
            {
              if ( !qword_18000D880 )
              {
                SendAppCommand(51);
                qword_18000D880 = SetTimer(hWndHidServ, 0x13u, INITIAL_WAIT, 0);
              }
            }
            else
            {
              KillTimer(hWndHidServ, 0x13u);
              qword_18000D880 = 0;
            }
            return ReleaseMutex(hMutexOOC);
          case 0x9Du:
            WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
            if ( v6 )
            {
              if ( !qword_18000D888 )
              {
                SendAppCommand(52);
                qword_18000D888 = SetTimer(hWndHidServ, 0x14u, INITIAL_WAIT, 0);
              }
            }
            else
            {
              KillTimer(hWndHidServ, 0x14u);
              qword_18000D888 = 0;
            }
            return ReleaseMutex(hMutexOOC);
          case 0xB0u:
            if ( !v6 )
              return result;
            v14 = 46;
            break;
          case 0xB1u:
            if ( !v6 )
              return result;
            v14 = 47;
            break;
          case 0xB2u:
            if ( !v6 )
              return result;
            v14 = 48;
            break;
          case 0xB3u:
            WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
            if ( v6 )
            {
              if ( !qword_18000D890 )
              {
                SendAppCommand(49);
                qword_18000D890 = SetTimer(hWndHidServ, 0x15u, INITIAL_WAIT, 0);
              }
            }
            else
            {
              KillTimer(hWndHidServ, 0x15u);
              qword_18000D890 = 0;
            }
            return ReleaseMutex(hMutexOOC);
          default:
LABEL_181:
            if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 4u )
            {
              v12 = 33;
              return WPP_SF_D(v8[2], v12, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v10);
            }
            return result;
        }
        return SendAppCommand(v14);
      }
      if ( v5 == 181 )
      {
        LOBYTE(v9) = -80;
        v15 = 12;
      }
      else
      {
        if ( v5 != 182 )
        {
          switch ( v5 )
          {
            case 0xB7u:
              LOBYTE(v8) = -78;
              break;
            case 0xCDu:
              LOBYTE(v8) = -77;
              break;
            case 0xD0u:
              if ( !v6 )
                return result;
              v14 = 55;
              return SendAppCommand(v14);
            default:
              goto LABEL_181;
          }
          return SendVK(v8, v6);
        }
        LOBYTE(v9) = -79;
        v15 = 11;
      }
      return HidRepeaterVKButtonDown(v15, v6, (__int64)v9);
    }
    result = 456;
    if ( v5 > 0x1C8u )
    {
      result = 551;
      if ( v5 <= 0x227u )
      {
        switch ( v5 )
        {
          case 0x227u:
            LOBYTE(v8) = -88;
            return SendVK(v8, v6);
          case 0x221u:
            LOBYTE(v8) = -86;
            return SendVK(v8, v6);
          case 0x223u:
            LOBYTE(v8) = -84;
            return SendVK(v8, v6);
          case 0x224u:
            LOBYTE(v9) = -90;
            v15 = 9;
            break;
          case 0x225u:
            LOBYTE(v9) = -89;
            v15 = 10;
            break;
          case 0x226u:
            LOBYTE(v8) = -87;
            return SendVK(v8, v6);
          default:
            goto LABEL_181;
        }
        return HidRepeaterVKButtonDown(v15, v6, (__int64)v9);
      }
      if ( v5 == 552 || v5 == 553 )
        return result;
      if ( v5 == 554 )
      {
        LOBYTE(v8) = -85;
        return SendVK(v8, v6);
      }
      v11 = (unsigned int)v5 - 711;
      if ( v5 == 711 )
      {
        if ( !v6 )
          return result;
        v16 = 0;
      }
      else
      {
        if ( v5 != 712 )
          goto LABEL_181;
        if ( !v6 )
          return result;
        v16 = 1;
      }
    }
    else
    {
      if ( v5 != 456 )
      {
        result = 341;
        if ( v5 <= 0x155u )
        {
          switch ( v5 )
          {
            case 0x155u:
              WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
              if ( v6 )
              {
                if ( !qword_18000D828 )
                {
                  SendAppCommand(22);
                  qword_18000D828 = SetTimer(hWndHidServ, 8u, INITIAL_WAIT, 0);
                }
              }
              else
              {
                KillTimer(hWndHidServ, 8u);
                qword_18000D828 = 0;
              }
              return ReleaseMutex(hMutexOOC);
            case 0xE9u:
              if ( (_BYTE)v13 )
              {
                WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
                if ( v6 )
                {
                  if ( !OOC_State[0] )
                  {
                    SendAppCommand(10);
                    OOC_State[0] = SetTimer(hWndHidServ, 3u, INITIAL_WAIT, 0);
                  }
                }
                else
                {
                  KillTimer(hWndHidServ, 3u);
                  OOC_State[0] = 0;
                }
                return ReleaseMutex(hMutexOOC);
              }
              LOBYTE(v9) = -81;
              v15 = 13;
              break;
            case 0xEAu:
              if ( (_BYTE)v13 )
              {
                WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
                if ( v6 )
                {
                  if ( !qword_18000D808 )
                  {
                    SendAppCommand(9);
                    qword_18000D808 = SetTimer(hWndHidServ, 4u, INITIAL_WAIT, 0);
                  }
                }
                else
                {
                  KillTimer(hWndHidServ, 4u);
                  qword_18000D808 = 0;
                }
                return ReleaseMutex(hMutexOOC);
              }
              LOBYTE(v9) = -82;
              v15 = 14;
              break;
            case 0x152u:
              WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
              if ( v6 )
              {
                if ( !qword_18000D810 )
                {
                  SendAppCommand(21);
                  qword_18000D810 = SetTimer(hWndHidServ, 5u, INITIAL_WAIT, 0);
                }
              }
              else
              {
                KillTimer(hWndHidServ, 5u);
                qword_18000D810 = 0;
              }
              return ReleaseMutex(hMutexOOC);
            case 0x153u:
              WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
              if ( v6 )
              {
                if ( !qword_18000D818 )
                {
                  SendAppCommand(19);
                  qword_18000D818 = SetTimer(hWndHidServ, 6u, INITIAL_WAIT, 0);
                }
              }
              else
              {
                KillTimer(hWndHidServ, 6u);
                qword_18000D818 = 0;
              }
              return ReleaseMutex(hMutexOOC);
            case 0x154u:
              WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
              if ( v6 )
              {
                if ( !qword_18000D820 )
                {
                  SendAppCommand(23);
                  qword_18000D820 = SetTimer(hWndHidServ, 7u, INITIAL_WAIT, 0);
                }
              }
              else
              {
                KillTimer(hWndHidServ, 7u);
                qword_18000D820 = 0;
              }
              return ReleaseMutex(hMutexOOC);
            default:
              goto LABEL_181;
          }
          return HidRepeaterVKButtonDown(v15, v6, (__int64)v9);
        }
        switch ( v5 )
        {
          case 0x183u:
            LOBYTE(v8) = -75;
            return SendVK(v8, v6);
          case 0x18Au:
            LOBYTE(v8) = -76;
            return SendVK(v8, v6);
          case 0x192u:
            LOBYTE(v8) = -73;
            return SendVK(v8, v6);
          case 0x194u:
            LOBYTE(v8) = -74;
            return SendVK(v8, v6);
        }
        if ( v5 != 454 )
          goto LABEL_181;
        memset_0(v18, 0, 0xE0u);
        v17 = 0x168696473LL;
        return RtlPublishWnfStateData(WNF_SPCH_REMOTE_SESSION_REQUEST, 0, &v17, 232, 0);
      }
      if ( !v6 )
        return result;
      v16 = 2;
    }
    return SendUIAction(v16, v11);
  }
  result = 154;
  if ( v5 == 154 )
  {
    if ( !v6 )
      return result;
    memset_0(v18, 0, 0xE0u);
    v17 = 1751737459;
    return RtlPublishWnfStateData(WNF_SPCH_REMOTE_SESSION_REQUEST, 0, &v17, 232, 0);
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 4u )
  {
    v10 = v5;
    v12 = 32;
    return WPP_SF_D(v8[2], v12, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180003594  mov     [rsp+arg_10], rbx
0x180003599  mov     [rsp+arg_18], rbp
0x18000359e  push    rsi
0x18000359f  push    rdi
0x1800035a0  push    r12
0x1800035a2  push    r14
0x1800035a4  push    r15
0x1800035a6  sub     rsp, 140h
0x1800035ad  mov     rax, cs:__security_cookie
0x1800035b4  xor     rax, rsp
0x1800035b7  mov     [rsp+168h+var_38], rax
0x1800035bf  mov     ebp, ecx
0x1800035c1  mov     r14d, edx
0x1800035c4  shr     ebp, 10h
0x1800035c7  mov     eax, 7FFFh
0x1800035cc  shr     r14d, 10h
0x1800035d0  movzx   esi, cx
0x1800035d3  and     si, ax
0x1800035d6  mov     ebx, edx
0x1800035d8  mov     edi, ecx
0x1800035da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035e1  lea     r8, WPP_GLOBAL_Control
0x1800035e8  mov     r15d, 4
0x1800035ee  cmp     rcx, r8
0x1800035f1  jz      short loc_18000362C
0x1800035f3  test    byte ptr [rcx+1Ch], 10h
0x1800035f7  jz      short loc_18000362C
0x1800035f9  cmp     [rcx+19h], r15b
0x1800035fd  jb      short loc_18000362C
0x1800035ff  mov     rcx, [rcx+10h]
0x180003603  mov     r9d, ebp
0x180003606  movsx   eax, bx
0x180003609  mov     [rsp+168h+var_138], eax
0x18000360d  movzx   edx, si
0x180003610  mov     [rsp+168h+var_140], edx
0x180003614  mov     dword ptr [rsp+168h+var_148], r14d
0x180003619  call    WPP_SF_DDDd
0x18000361e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003625  lea     r8, WPP_GLOBAL_Control
0x18000362c  mov     r12d, 1
0x180003632  cmp     bp, r12w
0x180003636  jnz     loc_180003F96
0x18000363c  xor     ebp, ebp
0x18000363e  mov     r9d, r14d
0x180003641  mov     edx, r14d
0x180003644  test    r14d, r14d
0x180003647  jz      loc_1800036E9
0x18000364d  sub     edx, r12d
0x180003650  jz      short loc_18000367D
0x180003652  cmp     edx, 0Bh
0x180003655  jz      loc_1800036E9
0x18000365b  cmp     rcx, r8
0x18000365e  jz      loc_180003FC6
0x180003664  test    byte ptr [rcx+1Ch], 10h
0x180003668  jz      loc_180003FC6
0x18000366e  cmp     [rcx+19h], r15b
0x180003672  jb      loc_180003FC6
0x180003678  lea     edx, [rbp+22h]
0x18000367b  jmp     short loc_1800036AB
0x18000367d  mov     eax, 9Ah
0x180003682  cmp     si, ax
0x180003685  jz      short loc_1800036C0
0x180003687  cmp     rcx, r8
0x18000368a  jz      loc_180003FC6
0x180003690  test    byte ptr [rcx+1Ch], 10h
0x180003694  jz      loc_180003FC6
0x18000369a  cmp     [rcx+19h], r15b
0x18000369e  jb      loc_180003FC6
0x1800036a4  movzx   r9d, si
0x1800036a8  lea     edx, [rax-7Ah]
0x1800036ab  mov     rcx, [rcx+10h]
0x1800036af  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x1800036b6  call    WPP_SF_D
0x1800036bb  jmp     loc_180003FC6
0x1800036c0  test    bx, bx
0x1800036c3  jz      loc_180003FC6
0x1800036c9  xor     edx, edx; Val
0x1800036cb  lea     rcx, [rsp+168h+var_120]; void *
0x1800036d0  mov     r8d, 0E0h; Size
0x1800036d6  call    memset_0
0x1800036db  mov     [rsp+168h+var_128], 68696473h
0x1800036e4  jmp     loc_180003E7C
0x1800036e9  shr     di, 0Fh
0x1800036ed  mov     eax, 0E7h
0x1800036f2  movzx   r9d, si
0x1800036f6  cmp     r9d, eax
0x1800036f9  ja      loc_180003B20
0x1800036ff  jz      loc_180003FC6
0x180003705  mov     eax, 0D1h
0x18000370a  cmp     r9d, eax
0x18000370d  ja      loc_1800039D5
0x180003713  jz      loc_1800039C2
0x180003719  cmp     r9d, 0B4h
0x180003720  ja      loc_180003961
0x180003726  jz      loc_1800038F0
0x18000372c  mov     edx, r9d
0x18000372f  sub     edx, 9Ch
0x180003735  jz      loc_18000387F
0x18000373b  sub     edx, r12d
0x18000373e  jz      loc_18000380E
0x180003744  sub     edx, 13h
0x180003747  jz      loc_1800037FB
0x18000374d  sub     edx, r12d
0x180003750  jz      loc_1800037E8
0x180003756  sub     edx, r12d
0x180003759  jz      short loc_1800037D5
0x18000375b  cmp     edx, r12d
0x18000375e  jnz     loc_180003F56
0x180003764  mov     rcx, cs:hMutexOOC; hHandle
0x18000376b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000376e  call    cs:__imp_WaitForSingleObject
0x180003774  test    bx, bx
0x180003777  jz      short loc_1800037B7
0x180003779  cmp     cs:qword_18000D890, rbp
0x180003780  jnz     loc_180003DB1
0x180003786  mov     ecx, 31h ; '1'
0x18000378b  call    SendAppCommand
0x180003790  mov     r8d, cs:INITIAL_WAIT; uElapse
0x180003797  xor     r9d, r9d; lpTimerFunc
0x18000379a  mov     rcx, cs:hWndHidServ; hWnd
0x1800037a1  lea     edx, [r9+15h]; nIDEvent
0x1800037a5  call    cs:__imp_SetTimer
0x1800037ab  mov     cs:qword_18000D890, rax
0x1800037b2  jmp     loc_180003DB1
0x1800037b7  mov     rcx, cs:hWndHidServ; hWnd
0x1800037be  mov     edx, 15h; uIDEvent
0x1800037c3  call    cs:__imp_KillTimer
0x1800037c9  mov     cs:qword_18000D890, rbp
0x1800037d0  jmp     loc_180003DB1
0x1800037d5  test    bx, bx
0x1800037d8  jz      loc_180003FC6
0x1800037de  mov     ecx, 30h ; '0'
0x1800037e3  jmp     loc_180003B09
0x1800037e8  test    bx, bx
0x1800037eb  jz      loc_180003FC6
0x1800037f1  mov     ecx, 2Fh ; '/'
0x1800037f6  jmp     loc_180003B09
0x1800037fb  test    bx, bx
0x1800037fe  jz      loc_180003FC6
0x180003804  mov     ecx, 2Eh ; '.'
0x180003809  jmp     loc_180003B09
0x18000380e  mov     rcx, cs:hMutexOOC; hHandle
0x180003815  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003818  call    cs:__imp_WaitForSingleObject
0x18000381e  test    bx, bx
0x180003821  jz      short loc_180003861
0x180003823  cmp     cs:qword_18000D888, rbp
0x18000382a  jnz     loc_180003DB1
0x180003830  mov     ecx, 34h ; '4'
0x180003835  call    SendAppCommand
0x18000383a  mov     r8d, cs:INITIAL_WAIT; uElapse
0x180003841  xor     r9d, r9d; lpTimerFunc
0x180003844  mov     rcx, cs:hWndHidServ; hWnd
0x18000384b  lea     edx, [r9+14h]; nIDEvent
0x18000384f  call    cs:__imp_SetTimer
0x180003855  mov     cs:qword_18000D888, rax
0x18000385c  jmp     loc_180003DB1
0x180003861  mov     rcx, cs:hWndHidServ; hWnd
0x180003868  mov     edx, 14h; uIDEvent
0x18000386d  call    cs:__imp_KillTimer
0x180003873  mov     cs:qword_18000D888, rbp
0x18000387a  jmp     loc_180003DB1
0x18000387f  mov     rcx, cs:hMutexOOC; hHandle
0x180003886  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003889  call    cs:__imp_WaitForSingleObject
0x18000388f  test    bx, bx
0x180003892  jz      short loc_1800038D2
0x180003894  cmp     cs:qword_18000D880, rbp
0x18000389b  jnz     loc_180003DB1
0x1800038a1  mov     ecx, 33h ; '3'
0x1800038a6  call    SendAppCommand
0x1800038ab  mov     r8d, cs:INITIAL_WAIT; uElapse
0x1800038b2  xor     r9d, r9d; lpTimerFunc
0x1800038b5  mov     rcx, cs:hWndHidServ; hWnd
0x1800038bc  lea     edx, [r9+13h]; nIDEvent
0x1800038c0  call    cs:__imp_SetTimer
0x1800038c6  mov     cs:qword_18000D880, rax
0x1800038cd  jmp     loc_180003DB1
0x1800038d2  mov     rcx, cs:hWndHidServ; hWnd
0x1800038d9  mov     edx, 13h; uIDEvent
0x1800038de  call    cs:__imp_KillTimer
0x1800038e4  mov     cs:qword_18000D880, rbp
0x1800038eb  jmp     loc_180003DB1
0x1800038f0  mov     rcx, cs:hMutexOOC; hHandle
0x1800038f7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800038fa  call    cs:__imp_WaitForSingleObject
0x180003900  test    bx, bx
0x180003903  jz      short loc_180003943
0x180003905  cmp     cs:qword_18000D898, rbp
0x18000390c  jnz     loc_180003DB1
0x180003912  mov     ecx, 32h ; '2'
0x180003917  call    SendAppCommand
0x18000391c  mov     r8d, cs:INITIAL_WAIT; uElapse
0x180003923  xor     r9d, r9d; lpTimerFunc
0x180003926  mov     rcx, cs:hWndHidServ; hWnd
0x18000392d  lea     edx, [r9+16h]; nIDEvent
0x180003931  call    cs:__imp_SetTimer
0x180003937  mov     cs:qword_18000D898, rax
0x18000393e  jmp     loc_180003DB1
0x180003943  mov     rcx, cs:hWndHidServ; hWnd
0x18000394a  mov     edx, 16h; uIDEvent
0x18000394f  call    cs:__imp_KillTimer
0x180003955  mov     cs:qword_18000D898, rbp
0x18000395c  jmp     loc_180003DB1
0x180003961  mov     edx, r9d
0x180003964  sub     edx, 0B5h
0x18000396a  jz      short loc_1800039AD
0x18000396c  sub     edx, r12d
0x18000396f  jz      short loc_1800039A3
0x180003971  sub     edx, r12d
0x180003974  jz      short loc_18000399C
0x180003976  sub     edx, 16h
0x180003979  jz      short loc_180003995
0x18000397b  cmp     edx, 3
0x18000397e  jnz     loc_180003F56
0x180003984  test    bx, bx
0x180003987  jz      loc_180003FC6
0x18000398d  lea     ecx, [rdx+34h]
0x180003990  jmp     loc_180003B09
0x180003995  mov     cl, 0B3h
0x180003997  jmp     loc_180003F8C
0x18000399c  mov     cl, 0B2h
0x18000399e  jmp     loc_180003F8C
0x1800039a3  mov     r8b, 0B1h
0x1800039a6  mov     ecx, 0Bh
0x1800039ab  jmp     short loc_1800039B5
0x1800039ad  mov     r8b, 0B0h
0x1800039b0  mov     ecx, 0Ch; uIDEvent
0x1800039b5  movzx   edx, bx
0x1800039b8  call    HidRepeaterVKButtonDown
0x1800039bd  jmp     loc_180003FC6
0x1800039c2  test    bx, bx
0x1800039c5  jz      loc_180003FC6
0x1800039cb  mov     ecx, 38h ; '8'
0x1800039d0  jmp     loc_180003B09
0x1800039d5  mov     eax, 0D7h
0x1800039da  cmp     r9d, eax
0x1800039dd  ja      loc_180003A7E
0x1800039e3  jz      loc_180003A6B
0x1800039e9  mov     edx, r9d
0x1800039ec  sub     edx, 0D2h
0x1800039f2  jz      short loc_180003A58
0x1800039f4  sub     edx, r12d
0x1800039f7  jz      short loc_180003A45
0x1800039f9  sub     edx, r12d
0x1800039fc  jz      short loc_180003A32
0x1800039fe  sub     edx, r12d
0x180003a01  jz      short loc_180003A1F
0x180003a03  cmp     edx, r12d
0x180003a06  jnz     loc_180003F56
0x180003a0c  test    bx, bx
0x180003a0f  jz      loc_180003FC6
0x180003a15  mov     ecx, 3Dh ; '='
0x180003a1a  jmp     loc_180003B09
0x180003a1f  test    bx, bx
0x180003a22  jz      loc_180003FC6
0x180003a28  mov     ecx, 3Ch ; '<'
0x180003a2d  jmp     loc_180003B09
0x180003a32  test    bx, bx
0x180003a35  jz      loc_180003FC6
0x180003a3b  mov     ecx, 3Bh ; ';'
0x180003a40  jmp     loc_180003B09
0x180003a45  test    bx, bx
0x180003a48  jz      loc_180003FC6
0x180003a4e  mov     ecx, 3Ah ; ':'
0x180003a53  jmp     loc_180003B09
0x180003a58  test    bx, bx
0x180003a5b  jz      loc_180003FC6
0x180003a61  mov     ecx, 39h ; '9'
0x180003a66  jmp     loc_180003B09
0x180003a6b  test    bx, bx
0x180003a6e  jz      loc_180003FC6
0x180003a74  mov     ecx, 3Eh ; '>'
0x180003a79  jmp     loc_180003B09
0x180003a7e  mov     edx, r9d
0x180003a81  sub     edx, 0E0h
0x180003a87  jz      short loc_180003AFF
0x180003a89  sub     edx, 2
0x180003a8c  jz      short loc_180003AE3
0x180003a8e  sub     edx, r12d
0x180003a91  jz      short loc_180003ACA
0x180003a93  sub     edx, r12d
0x180003a96  jz      short loc_180003AB1
0x180003a98  cmp     edx, r12d
0x180003a9b  jnz     loc_180003F56
0x180003aa1  test    bx, bx
0x180003aa4  jz      loc_180003FC6
0x180003aaa  mov     ecx, 14h
0x180003aaf  jmp     short loc_180003B09
0x180003ab1  test    bx, bx
0x180003ab4  jle     short loc_180003ABD
0x180003ab6  mov     ecx, 17h
0x180003abb  jmp     short loc_180003B09
0x180003abd  jns     loc_180003FC6
0x180003ac3  mov     ecx, 16h
0x180003ac8  jmp     short loc_180003B09
0x180003aca  test    bx, bx
0x180003acd  jle     short loc_180003AD6
0x180003acf  mov     ecx, 15h
0x180003ad4  jmp     short loc_180003B09
  ... truncated ...
```
