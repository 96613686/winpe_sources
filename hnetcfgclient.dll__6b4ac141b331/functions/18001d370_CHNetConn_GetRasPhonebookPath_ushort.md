# CHNetConn::GetRasPhonebookPath(ushort * *)

- ea: `0x18001d370`
- end: `0x18001d5f3`
- name: `?GetRasPhonebookPath@CHNetConn@@UEAAJPEAPEAG@Z`
- size: `643`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005698`
- `0x18000a45c`
- `0x18000a484`
- `0x18001b110`
- `0x18001d370`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001d541`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d541`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3d4`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3d4`
- `OLEAUT32!__imp_VariantClear` at `0x18001d5a6`
- `OLEAUT32!__imp_VariantClear` at `0x18001d5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d54f`

## string_xrefs

- `0x18001d4c6`: `PhonebookPath`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetRasPhonebookPath(CHNetConn *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  int ConnectionObject; // eax
  int v9; // eax
  __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  struct IWbemClassObject *v14; // [rsp+80h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  v14 = 0;
  VariantInit(&pvarg);
  if ( a2 )
  {
    v4 = 0;
    *a2 = 0;
LABEL_11:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  v4 = -2147467261;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147500035LL);
    goto LABEL_11;
  }
LABEL_12:
  if ( *((_BYTE *)this + 96) == 1 )
  {
    v4 = -2147418113;
    if ( v5 == &WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 2u )
    {
      v6 = 64;
      v7 = 2147549183LL;
      goto LABEL_17;
    }
  }
  else if ( !v4 )
  {
    ConnectionObject = CHNetConn::GetConnectionObject(this, &v14);
    v4 = ConnectionObject;
    if ( ConnectionObject >= 0 )
    {
      if ( !ConnectionObject )
      {
        v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v14->lpVtbl->Get)(
               v14,
               L"PhonebookPath",
               0,
               &pvarg,
               0,
               0);
        v4 = v9;
        if ( v9 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v9);
        }
        ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
        if ( !v4 )
        {
          if ( pvarg.vt == 8 )
          {
            v10 = SysStringLen(pvarg.bstrVal) + 1;
            v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
            *a2 = v11;
            if ( v11 )
            {
              StringCchCopyW(v11, (unsigned int)v10, pvarg.bstrVal);
            }
            else
            {
              v4 = -2147024882;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  67,
                  WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                  2147942414LL);
              }
            }
            VariantClear(&pvarg);
          }
          else
          {
            v4 = -2147217406;
          }
        }
      }
      goto LABEL_40;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_41;
    v6 = 65;
    v7 = (unsigned int)ConnectionObject;
LABEL_17:
    WPP_SF_d(v5[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
LABEL_40:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_41:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 68, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18001d370  mov     [rsp-18h+arg_8], rbx
0x18001d375  mov     [rsp-18h+arg_10], rsi
0x18001d37a  push    rbp
0x18001d37b  push    rdi
0x18001d37c  push    r12
0x18001d37e  mov     rbp, rsp
0x18001d381  sub     rsp, 60h
0x18001d385  mov     rsi, rdx
0x18001d388  mov     rdi, rcx
0x18001d38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d392  lea     r12, WPP_GLOBAL_Control
0x18001d399  cmp     rcx, r12
0x18001d39c  jz      short loc_18001D3BF
0x18001d39e  test    byte ptr [rcx+1Ch], 8
0x18001d3a2  jz      short loc_18001D3BF
0x18001d3a4  cmp     byte ptr [rcx+19h], 6
0x18001d3a8  jb      short loc_18001D3BF
0x18001d3aa  mov     rcx, [rcx+10h]
0x18001d3ae  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d3b5  mov     edx, 3Eh ; '>'
0x18001d3ba  call    WPP_SF_
0x18001d3bf  xor     eax, eax
0x18001d3c1  lea     rcx, [rbp+pvarg]; pvarg
0x18001d3c5  xorps   xmm0, xmm0
0x18001d3c8  mov     qword ptr [rbp+pvarg+10h], rax
0x18001d3cc  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d3d0  mov     [rbp+arg_0], rax
0x18001d3d4  call    cs:__imp_VariantInit
0x18001d3da  test    rsi, rsi
0x18001d3dd  jz      short loc_18001D3E6
0x18001d3df  xor     ebx, ebx
0x18001d3e1  mov     [rsi], rbx
0x18001d3e4  jmp     short loc_18001D41B
0x18001d3e6  mov     ebx, 80004003h
0x18001d3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3f2  cmp     rcx, r12
0x18001d3f5  jz      short loc_18001D422
0x18001d3f7  test    byte ptr [rcx+1Ch], 8
0x18001d3fb  jz      short loc_18001D422
0x18001d3fd  cmp     byte ptr [rcx+19h], 2
0x18001d401  jb      short loc_18001D422
0x18001d403  mov     rcx, [rcx+10h]
0x18001d407  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d40e  mov     edx, 3Fh ; '?'
0x18001d413  mov     r9d, ebx
0x18001d416  call    WPP_SF_d
0x18001d41b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d422  cmp     byte ptr [rdi+60h], 1
0x18001d426  jnz     short loc_18001D467
0x18001d428  mov     ebx, 8000FFFFh
0x18001d42d  cmp     rcx, r12
0x18001d430  jz      loc_18001D5DC
0x18001d436  test    byte ptr [rcx+1Ch], 8
0x18001d43a  jz      loc_18001D5B3
0x18001d440  cmp     byte ptr [rcx+19h], 2
0x18001d444  jb      loc_18001D5B3
0x18001d44a  mov     edx, 40h ; '@'
0x18001d44f  mov     r9d, ebx
0x18001d452  mov     rcx, [rcx+10h]
0x18001d456  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d45d  call    WPP_SF_d
0x18001d462  jmp     loc_18001D5AC
0x18001d467  test    ebx, ebx
0x18001d469  jnz     loc_18001D5B3
0x18001d46f  lea     rdx, [rbp+arg_0]; struct IWbemClassObject **
0x18001d473  mov     rcx, rdi; this
0x18001d476  call    ?GetConnectionObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionObject(IWbemClassObject * *)
0x18001d47b  mov     ebx, eax
0x18001d47d  test    eax, eax
0x18001d47f  jns     short loc_18001D4AF
0x18001d481  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d488  cmp     rcx, r12
0x18001d48b  jz      loc_18001D5DC
0x18001d491  test    byte ptr [rcx+1Ch], 8
0x18001d495  jz      loc_18001D5B3
0x18001d49b  cmp     byte ptr [rcx+19h], 2
0x18001d49f  jb      loc_18001D5B3
0x18001d4a5  mov     edx, 41h ; 'A'
0x18001d4aa  mov     r9d, eax
0x18001d4ad  jmp     short loc_18001D452
0x18001d4af  jnz     loc_18001D5AC
0x18001d4b5  mov     rcx, [rbp+arg_0]
0x18001d4b9  lea     r9, [rbp+pvarg]
0x18001d4bd  mov     [rsp+60h+var_38], 0
0x18001d4c6  lea     rdx, ?c_wszPhonebookPath@@3QBGB; "PhonebookPath"
0x18001d4cd  xor     r8d, r8d
0x18001d4d0  mov     [rsp+60h+var_40], 0
0x18001d4d9  mov     rax, [rcx]
0x18001d4dc  mov     rax, [rax+20h]
0x18001d4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4e5  mov     ebx, eax
0x18001d4e7  test    eax, eax
0x18001d4e9  jns     short loc_18001D51B
0x18001d4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4f2  cmp     rcx, r12
0x18001d4f5  jz      short loc_18001D51B
0x18001d4f7  test    byte ptr [rcx+1Ch], 8
0x18001d4fb  jz      short loc_18001D51B
0x18001d4fd  cmp     byte ptr [rcx+19h], 2
0x18001d501  jb      short loc_18001D51B
0x18001d503  mov     rcx, [rcx+10h]
0x18001d507  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d50e  mov     edx, 42h ; 'B'
0x18001d513  mov     r9d, eax
0x18001d516  call    WPP_SF_d
0x18001d51b  mov     rcx, [rbp+arg_0]
0x18001d51f  mov     rax, [rcx]
0x18001d522  mov     rax, [rax+10h]
0x18001d526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d52b  test    ebx, ebx
0x18001d52d  jnz     short loc_18001D5AC
0x18001d52f  cmp     word ptr [rbp+pvarg], 8
0x18001d534  jz      short loc_18001D53D
0x18001d536  mov     ebx, 80041002h
0x18001d53b  jmp     short loc_18001D5AC
0x18001d53d  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18001d541  call    cs:__imp_SysStringLen
0x18001d547  inc     eax
0x18001d549  mov     edi, eax
0x18001d54b  lea     rcx, [rax+rax]; cb
0x18001d54f  call    cs:__imp_CoTaskMemAlloc
0x18001d555  mov     [rsi], rax
0x18001d558  test    rax, rax
0x18001d55b  jz      short loc_18001D56D
0x18001d55d  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x18001d561  mov     edx, edi; unsigned __int64
0x18001d563  mov     rcx, rax; unsigned __int16 *
0x18001d566  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d56b  jmp     short loc_18001D5A2
0x18001d56d  mov     ebx, 8007000Eh
0x18001d572  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d579  cmp     rcx, r12
0x18001d57c  jz      short loc_18001D5A2
0x18001d57e  test    byte ptr [rcx+1Ch], 8
0x18001d582  jz      short loc_18001D5A2
0x18001d584  cmp     byte ptr [rcx+19h], 2
0x18001d588  jb      short loc_18001D5A2
0x18001d58a  mov     rcx, [rcx+10h]
0x18001d58e  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d595  mov     edx, 43h ; 'C'
0x18001d59a  mov     r9d, ebx
0x18001d59d  call    WPP_SF_d
0x18001d5a2  lea     rcx, [rbp+pvarg]; pvarg
0x18001d5a6  call    cs:__imp_VariantClear
0x18001d5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5b3  cmp     rcx, r12
0x18001d5b6  jz      short loc_18001D5DC
0x18001d5b8  test    byte ptr [rcx+1Ch], 8
0x18001d5bc  jz      short loc_18001D5DC
0x18001d5be  cmp     byte ptr [rcx+19h], 6
0x18001d5c2  jb      short loc_18001D5DC
0x18001d5c4  mov     rcx, [rcx+10h]
0x18001d5c8  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001d5cf  mov     edx, 44h ; 'D'
0x18001d5d4  mov     r9d, ebx
0x18001d5d7  call    WPP_SF_d
0x18001d5dc  lea     r11, [rsp+60h+var_s0]
0x18001d5e1  mov     eax, ebx
0x18001d5e3  mov     rbx, [r11+28h]
0x18001d5e7  mov     rsi, [r11+30h]
0x18001d5eb  mov     rsp, r11
0x18001d5ee  pop     r12
0x18001d5f0  pop     rdi
0x18001d5f1  pop     rbp
0x18001d5f2  retn
```
