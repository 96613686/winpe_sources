# CHNetConn::Initialize(IWbemServices *,IWbemClassObject *)

- ea: `0x18001da54`
- end: `0x18001dcc2`
- name: `?Initialize@CHNetConn@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct IWbemServices *, struct IWbemClassObject *)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180015e50`
- `0x180016060`
- `0x180016270`
- `0x180016480`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001b110`
- `0x18001da54`
- `0x180028f88`
- `0x180029a74`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001dac2`
- `OLEAUT32!__imp_VariantInit` at `0x18001dba5`
- `OLEAUT32!__imp_VariantInit` at `0x18001dac2`
- `OLEAUT32!__imp_VariantInit` at `0x18001dba5`

## pseudocode

```c
__int64 __fastcall CHNetConn::Initialize(CHNetConn *this, struct IWbemServices *a2, struct IWbemClassObject *a3)
{
  int WmiPathFromObject; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  int ConnectionObject; // eax
  int BooleanValue; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-58h] BYREF
  struct IWbemClassObject *v14; // [rsp+A0h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v14 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *((_QWORD *)this + 8) = a2;
  ((void (__fastcall *)(struct IWbemServices *))a2->lpVtbl->AddRef)(a2);
  WmiPathFromObject = GetWmiPathFromObject(a3, (unsigned __int16 **)this + 10);
  v7 = WmiPathFromObject;
  if ( WmiPathFromObject >= 0 )
  {
    if ( WmiPathFromObject )
      goto LABEL_33;
    WmiPathFromObject = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
                          a3,
                          L"Connection",
                          0,
                          &pvarg,
                          0,
                          0);
    v7 = WmiPathFromObject;
    if ( WmiPathFromObject < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_34;
      v9 = 20;
      goto LABEL_10;
    }
    if ( WmiPathFromObject )
      goto LABEL_33;
    *((_QWORD *)this + 9) = pvarg.llVal;
    VariantInit(&pvarg);
    ConnectionObject = CHNetConn::GetConnectionObject(this, &v14);
    v7 = ConnectionObject;
    if ( ConnectionObject < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)ConnectionObject);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
    if ( v7 == -2147217406 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 128LL))(
        *((_QWORD *)this + 8),
        *((_QWORD *)this + 10),
        0,
        0,
        0);
      goto LABEL_33;
    }
    if ( !v7 )
    {
      BooleanValue = GetBooleanValue(v14, L"IsLanConnection", (bool *)this + 96);
      v7 = BooleanValue;
      if ( BooleanValue < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)BooleanValue);
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 19;
LABEL_10:
    WPP_SF_d(v8[2], v9, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)WmiPathFromObject);
LABEL_33:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 23, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001da54  push    rbx
0x18001da56  push    rsi
0x18001da57  push    rdi
0x18001da58  push    r12
0x18001da5a  push    r13
0x18001da5c  push    r14
0x18001da5e  sub     rsp, 68h
0x18001da62  mov     rsi, r8
0x18001da65  mov     rbx, rdx
0x18001da68  mov     rdi, rcx
0x18001da6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da72  lea     r12, WPP_GLOBAL_Control
0x18001da79  lea     r13, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001da80  cmp     rcx, r12
0x18001da83  jz      short loc_18001DAA2
0x18001da85  test    byte ptr [rcx+1Ch], 8
0x18001da89  jz      short loc_18001DAA2
0x18001da8b  cmp     byte ptr [rcx+19h], 6
0x18001da8f  jb      short loc_18001DAA2
0x18001da91  mov     rcx, [rcx+10h]
0x18001da95  mov     edx, 12h
0x18001da9a  mov     r8, r13
0x18001da9d  call    WPP_SF_
0x18001daa2  xorps   xmm0, xmm0
0x18001daa5  mov     [rsp+98h+arg_0], 0
0x18001dab1  xor     eax, eax
0x18001dab3  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18001dab8  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18001dabd  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18001dac2  call    cs:__imp_VariantInit
0x18001dac8  mov     [rdi+40h], rbx
0x18001dacc  mov     rcx, rbx
0x18001dacf  mov     rax, [rbx]
0x18001dad2  mov     rax, [rax+8]
0x18001dad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dadb  lea     rdx, [rdi+50h]; unsigned __int16 **
0x18001dadf  mov     rcx, rsi; struct IWbemClassObject *
0x18001dae2  call    ?GetWmiPathFromObject@@YAJPEAUIWbemClassObject@@PEAPEAG@Z; GetWmiPathFromObject(IWbemClassObject *,ushort * *)
0x18001dae7  mov     ebx, eax
0x18001dae9  test    eax, eax
0x18001daeb  jns     short loc_18001DB2A
0x18001daed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daf4  cmp     rcx, r12
0x18001daf7  jz      loc_18001DCB2
0x18001dafd  test    byte ptr [rcx+1Ch], 8
0x18001db01  jz      loc_18001DC8D
0x18001db07  cmp     byte ptr [rcx+19h], 2
0x18001db0b  jb      loc_18001DC8D
0x18001db11  mov     edx, 13h
0x18001db16  mov     rcx, [rcx+10h]
0x18001db1a  mov     r9d, eax
0x18001db1d  mov     r8, r13
0x18001db20  call    WPP_SF_d
0x18001db25  jmp     loc_18001DC86
0x18001db2a  jnz     loc_18001DC86
0x18001db30  mov     rax, [rsi]
0x18001db33  lea     r9, [rsp+98h+pvarg]
0x18001db38  mov     [rsp+98h+var_70], 0
0x18001db41  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x18001db48  xor     r8d, r8d
0x18001db4b  mov     [rsp+98h+var_78], 0
0x18001db54  mov     rcx, rsi
0x18001db57  mov     rax, [rax+20h]
0x18001db5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db60  mov     ebx, eax
0x18001db62  test    eax, eax
0x18001db64  jns     short loc_18001DB91
0x18001db66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db6d  cmp     rcx, r12
0x18001db70  jz      loc_18001DCB2
0x18001db76  test    byte ptr [rcx+1Ch], 8
0x18001db7a  jz      loc_18001DC8D
0x18001db80  cmp     byte ptr [rcx+19h], 2
0x18001db84  jb      loc_18001DC8D
0x18001db8a  mov     edx, 14h
0x18001db8f  jmp     short loc_18001DB16
0x18001db91  jnz     loc_18001DC86
0x18001db97  mov     rax, qword ptr [rsp+98h+pvarg+8]
0x18001db9c  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18001dba1  mov     [rdi+48h], rax
0x18001dba5  call    cs:__imp_VariantInit
0x18001dbab  lea     rdx, [rsp+98h+arg_0]; struct IWbemClassObject **
0x18001dbb3  mov     rcx, rdi; this
0x18001dbb6  call    ?GetConnectionObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionObject(IWbemClassObject * *)
0x18001dbbb  mov     ebx, eax
0x18001dbbd  test    eax, eax
0x18001dbbf  jns     short loc_18001DBED
0x18001dbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbc8  cmp     rcx, r12
0x18001dbcb  jz      short loc_18001DBF4
0x18001dbcd  test    byte ptr [rcx+1Ch], 8
0x18001dbd1  jz      short loc_18001DBF4
0x18001dbd3  cmp     byte ptr [rcx+19h], 2
0x18001dbd7  jb      short loc_18001DBF4
0x18001dbd9  mov     rcx, [rcx+10h]
0x18001dbdd  mov     edx, 15h
0x18001dbe2  mov     r9d, eax
0x18001dbe5  mov     r8, r13
0x18001dbe8  call    WPP_SF_d
0x18001dbed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbf4  cmp     ebx, 80041002h
0x18001dbfa  jnz     short loc_18001DC24
0x18001dbfc  mov     rcx, [rdi+40h]
0x18001dc00  xor     r9d, r9d
0x18001dc03  mov     rdx, [rdi+50h]
0x18001dc07  xor     r8d, r8d
0x18001dc0a  mov     [rsp+98h+var_78], 0
0x18001dc13  mov     rax, [rcx]
0x18001dc16  mov     rax, [rax+80h]
0x18001dc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc22  jmp     short loc_18001DC86
0x18001dc24  test    ebx, ebx
0x18001dc26  jnz     short loc_18001DC8D
0x18001dc28  mov     rcx, [rsp+98h+arg_0]; struct IWbemClassObject *
0x18001dc30  lea     r8, [rdi+60h]; unsigned __int8 *
0x18001dc34  lea     rdx, ?c_wszIsLanConnection@@3QBGB; "IsLanConnection"
0x18001dc3b  call    ?GetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGPEAE@Z; GetBooleanValue(IWbemClassObject *,ushort const *,uchar *)
0x18001dc40  mov     ebx, eax
0x18001dc42  test    eax, eax
0x18001dc44  jns     short loc_18001DC72
0x18001dc46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc4d  cmp     rcx, r12
0x18001dc50  jz      short loc_18001DC72
0x18001dc52  test    byte ptr [rcx+1Ch], 8
0x18001dc56  jz      short loc_18001DC72
0x18001dc58  cmp     byte ptr [rcx+19h], 2
0x18001dc5c  jb      short loc_18001DC72
0x18001dc5e  mov     rcx, [rcx+10h]
0x18001dc62  mov     edx, 16h
0x18001dc67  mov     r9d, eax
0x18001dc6a  mov     r8, r13
0x18001dc6d  call    WPP_SF_d
0x18001dc72  mov     rcx, [rsp+98h+arg_0]
0x18001dc7a  mov     rax, [rcx]
0x18001dc7d  mov     rax, [rax+10h]
0x18001dc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc8d  cmp     rcx, r12
0x18001dc90  jz      short loc_18001DCB2
0x18001dc92  test    byte ptr [rcx+1Ch], 8
0x18001dc96  jz      short loc_18001DCB2
0x18001dc98  cmp     byte ptr [rcx+19h], 6
0x18001dc9c  jb      short loc_18001DCB2
0x18001dc9e  mov     rcx, [rcx+10h]
0x18001dca2  mov     edx, 17h
0x18001dca7  mov     r9d, ebx
0x18001dcaa  mov     r8, r13
0x18001dcad  call    WPP_SF_d
0x18001dcb2  mov     eax, ebx
0x18001dcb4  add     rsp, 68h
0x18001dcb8  pop     r14
0x18001dcba  pop     r13
0x18001dcbc  pop     r12
0x18001dcbe  pop     rdi
0x18001dcbf  pop     rsi
0x18001dcc0  pop     rbx
0x18001dcc1  retn
```
