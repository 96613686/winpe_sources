# CImpIRowsetLocate::Compare(ulong,ulong,uchar const *,ulong,uchar const *,ulong *)

- ea: `0x10031490`
- end: `0x10031642`
- name: `?Compare@CImpIRowsetLocate@@UAGJKKPBEK0PAK@Z`
- size: `434`
- prototype: `int(CImpIRowsetLocate *__hidden this, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x10031490`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10031626`
- `KERNEL32!LeaveCriticalSection` at `0x10031626`
- `KERNEL32!EnterCriticalSection` at `0x10031528`
- `KERNEL32!EnterCriticalSection` at `0x10031528`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100314be`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100314be`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003160a`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003160a`

## pseudocode

```c
int __stdcall CImpIRowsetLocate::Compare(
        CImpIRowsetLocate *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int *a7)
{
  int v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // esi
  struct _RTL_CRITICAL_SECTION *v9; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v11; // ecx
  int isZombie; // eax
  int v13; // ecx
  const struct _GUID *v15; // [esp+0h] [ebp-24h]
  int v16; // [esp+4h] [ebp-20h]
  _BYTE v17[4]; // [esp+10h] [ebp-14h] BYREF
  struct _RTL_CRITICAL_SECTION *v18; // [esp+14h] [ebp-10h]
  int v19; // [esp+20h] [ebp-4h]

  v7 = 0;
  SetErrorInfo(0, 0);
  v8 = 0;
  v18 = 0;
  v19 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)this + 2);
  LockSemaphore = v9[2].LockSemaphore;
  if ( LockSemaphore
    && (LockSemaphore[4] != 1 || (v11 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v11)),
        isZombie == 1)
    || !v9[4].SpinCount && !v9[9].SpinCount )
  {
    v7 = -2147418113;
    goto LABEL_38;
  }
  if ( ((int)v9[4].DebugInfo & 0x400) != 0 )
  {
    v7 = -2147217888;
    goto LABEL_38;
  }
  v8 = v9 + 3;
  v18 = v9 + 3;
  EnterCriticalSection(v9 + 3);
  if ( a3 && a5 && a4 && a6 && a7 )
  {
    if ( a3 == 1 || a3 == 4 )
    {
      if ( a5 != 1 && a5 != 4 )
      {
        v7 = -2147217906;
        goto LABEL_38;
      }
      if ( (a3 != 4 || *(_DWORD *)a4) && (a5 != 4 || *(_DWORD *)a6) && (a3 != 1 || *a4) && (a5 != 1 || *a6) )
      {
        if ( a3 == a5 )
        {
          v13 = 0;
          if ( a3 == 4 )
            LOBYTE(v13) = *(_DWORD *)a4 != *(_DWORD *)a6;
          else
            LOBYTE(v13) = *a4 != *a6;
          *a7 = 2 * v13 + 1;
        }
        else
        {
          *a7 = 3;
        }
        goto LABEL_40;
      }
    }
    v7 = -2147217906;
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_38:
  if ( !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 56) + 20),
          v17,
          4,
          3) )
    CExtError::SendHRtoOLEAuto(v7, (__int128 *)&IID_IRowsetLocate, 0, v15, v16);
LABEL_40:
  if ( v8 )
    LeaveCriticalSection(v8);
  return v7;
}

```

## disassembly

```asm
0x10031490  mov     edi, edi
0x10031492  push    ebp
0x10031493  mov     ebp, esp
0x10031495  push    0FFFFFFFFh
0x10031497  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1003149c  mov     eax, large fs:0
0x100314a2  push    eax
0x100314a3  sub     esp, 8
0x100314a6  push    ebx
0x100314a7  push    esi
0x100314a8  push    edi; int
0x100314a9  mov     eax, ___security_cookie
0x100314ae  xor     eax, ebp
0x100314b0  push    eax; struct _GUID *
0x100314b1  lea     eax, [ebp+var_C]
0x100314b4  mov     large fs:0, eax
0x100314ba  xor     edi, edi
0x100314bc  push    edi; perrinfo
0x100314bd  push    edi; dwReserved
0x100314be  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100314c4  xor     esi, esi
0x100314c6  mov     [ebp+var_10], esi
0x100314c9  mov     edx, [ebp+this]
0x100314cc  mov     [ebp+var_4], esi
0x100314cf  mov     edx, [edx+8]
0x100314d2  mov     eax, [edx+40h]
0x100314d5  test    eax, eax
0x100314d7  jz      short loc_100314F5
0x100314d9  cmp     dword ptr [eax+10h], 1
0x100314dd  jnz     short loc_100314ED
0x100314df  mov     ecx, [eax+8]; this
0x100314e2  test    ecx, ecx
0x100314e4  jz      short loc_100314ED
0x100314e6  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x100314eb  jmp     short loc_100314F0
0x100314ed  mov     eax, [eax+0Ch]
0x100314f0  cmp     eax, 1
0x100314f3  jz      short loc_10031504
0x100314f5  cmp     dword ptr [edx+74h], 0
0x100314f9  jnz     short loc_1003150E
0x100314fb  cmp     dword ptr [edx+0ECh], 0
0x10031502  jnz     short loc_1003150E
0x10031504  mov     edi, 8000FFFFh
0x10031509  jmp     loc_100315F3
0x1003150e  test    dword ptr [edx+60h], 400h
0x10031515  jz      short loc_10031521
0x10031517  mov     edi, 80040E20h
0x1003151c  jmp     loc_100315F3
0x10031521  lea     esi, [edx+48h]
0x10031524  push    esi; lpCriticalSection
0x10031525  mov     [ebp+var_10], esi
0x10031528  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003152e  mov     eax, [ebp+arg_8]
0x10031531  test    eax, eax
0x10031533  jz      loc_100315EE
0x10031539  mov     ecx, [ebp+arg_10]
0x1003153c  test    ecx, ecx
0x1003153e  jz      loc_100315EE
0x10031544  mov     edx, [ebp+arg_C]
0x10031547  test    edx, edx
0x10031549  jz      loc_100315EE
0x1003154f  mov     ebx, [ebp+arg_14]
0x10031552  test    ebx, ebx
0x10031554  jz      loc_100315EE
0x1003155a  cmp     [ebp+arg_18], 0
0x1003155e  jz      loc_100315EE
0x10031564  cmp     eax, 1
0x10031567  jz      short loc_1003156E
0x10031569  cmp     eax, 4
0x1003156c  jnz     short loc_100315A7
0x1003156e  cmp     ecx, 1
0x10031571  jz      short loc_1003157F
0x10031573  cmp     ecx, 4
0x10031576  jz      short loc_1003157F
0x10031578  mov     edi, 80040E0Eh
0x1003157d  jmp     short loc_100315F3
0x1003157f  cmp     eax, 4
0x10031582  jnz     short loc_10031589
0x10031584  cmp     dword ptr [edx], 0
0x10031587  jz      short loc_100315A7
0x10031589  cmp     ecx, 4
0x1003158c  jnz     short loc_10031593
0x1003158e  cmp     dword ptr [ebx], 0
0x10031591  jz      short loc_100315A7
0x10031593  cmp     eax, 1
0x10031596  jnz     short loc_1003159D
0x10031598  cmp     byte ptr [edx], 0
0x1003159b  jz      short loc_100315A7
0x1003159d  cmp     ecx, 1
0x100315a0  jnz     short loc_100315AE
0x100315a2  cmp     byte ptr [ebx], 0
0x100315a5  jnz     short loc_100315AE
0x100315a7  mov     edi, 80040E0Eh
0x100315ac  jmp     short loc_100315F3
0x100315ae  cmp     eax, ecx
0x100315b0  jz      short loc_100315BD
0x100315b2  mov     eax, [ebp+arg_18]
0x100315b5  mov     dword ptr [eax], 3
0x100315bb  jmp     short loc_10031621
0x100315bd  xor     ecx, ecx
0x100315bf  cmp     eax, 4
0x100315c2  jnz     short loc_100315D9
0x100315c4  mov     eax, [edx]
0x100315c6  cmp     eax, [ebx]
0x100315c8  mov     eax, [ebp+arg_18]
0x100315cb  setnz   cl
0x100315ce  lea     ecx, ds:1[ecx*2]
0x100315d5  mov     [eax], ecx
0x100315d7  jmp     short loc_10031621
0x100315d9  mov     al, [edx]
0x100315db  cmp     al, [ebx]
0x100315dd  mov     eax, [ebp+arg_18]
0x100315e0  setnz   cl
0x100315e3  lea     ecx, ds:1[ecx*2]
0x100315ea  mov     [eax], ecx
0x100315ec  jmp     short loc_10031621
0x100315ee  mov     edi, 80070057h
0x100315f3  mov     eax, [ebp+this]
0x100315f6  lea     ecx, [ebp+var_14]
0x100315f9  push    3
0x100315fb  push    4
0x100315fd  push    ecx
0x100315fe  mov     eax, [eax+8]
0x10031601  mov     eax, [eax+38h]
0x10031604  push    dword ptr [eax+14h]
0x10031607  push    dword ptr [eax+10h]
0x1003160a  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10031610  test    eax, eax
0x10031612  jnz     short loc_10031621
0x10031614  push    eax; int
0x10031615  push    offset _IID_IRowsetLocate; int
0x1003161a  mov     edx, edi
0x1003161c  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10031621  test    esi, esi
0x10031623  jz      short loc_1003162C
0x10031625  push    esi; lpCriticalSection
0x10031626  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003162c  mov     eax, edi
0x1003162e  mov     ecx, [ebp+var_C]
0x10031631  mov     large fs:0, ecx
0x10031638  pop     ecx
0x10031639  pop     edi
0x1003163a  pop     esi
0x1003163b  pop     ebx
0x1003163c  mov     esp, ebp
0x1003163e  pop     ebp
0x1003163f  retn    1Ch
0x1004ddb0  lea     ecx, [ebp+var_10]; this
0x1004ddb3  jmp     ??1CMutex@@QAE@XZ
0x1004ddbd  nop
0x1004ddbe  nop
0x1004ddbf  mov     edx, [esp-4+arg_4]
0x1004ddc3  lea     eax, [edx+0Ch]
0x1004ddc6  mov     ecx, [edx-18h]
0x1004ddc9  xor     ecx, eax; StackCookie
0x1004ddcb  call    @__security_check_cookie@4
0x1004ddd0  mov     eax, offset stru_1004F3AC
0x1004ddd5  jmp     ___CxxFrameHandler3
```
