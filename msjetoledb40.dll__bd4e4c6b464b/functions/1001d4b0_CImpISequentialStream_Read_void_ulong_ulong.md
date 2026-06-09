# CImpISequentialStream::Read(void *,ulong,ulong *)

- ea: `0x1001d4b0`
- end: `0x1001d63b`
- name: `?Read@CImpISequentialStream@@UAGJPAXKPAK@Z`
- size: `395`
- prototype: `int __stdcall(CImpISequentialStream *__hidden this, void *, unsigned int cbData, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001c6d0`
- `0x1001d4b0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001d615`
- `KERNEL32!LeaveCriticalSection` at `0x1001d615`
- `KERNEL32!EnterCriticalSection` at `0x1001d538`
- `KERNEL32!EnterCriticalSection` at `0x1001d538`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001d5e2`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001d5e2`

## pseudocode

```c
int __stdcall CImpISequentialStream::Read(CImpISequentialStream *this, void *a2, unsigned int cbData, unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v5; // esi
  int v6; // ebx
  _DWORD *v7; // eax
  CTransactionState *v8; // ecx
  int isZombie; // eax
  int v10; // ebx
  CImpISequentialStream *v11; // ebx
  JET_ERR v12; // eax
  unsigned int v13; // ecx
  unsigned int pcbActual; // [esp+1Ch] [ebp-28h] BYREF
  CImpISequentialStream *v15; // [esp+20h] [ebp-24h]
  JET_RETINFO pretinfo; // [esp+24h] [ebp-20h] BYREF
  int v17; // [esp+40h] [ebp-4h]

  v15 = this;
  pcbActual = 0;
  v17 = 0;
  if ( a4 )
    *a4 = 0;
  if ( *((_DWORD *)this + 2) == 1 )
    return -2147418113;
  v5 = (struct _RTL_CRITICAL_SECTION *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 4) + 16))(*((_DWORD *)this + 4));
  EnterCriticalSection(v5);
  v6 = *((_DWORD *)this + 4);
  pretinfo.ibLongValue = *((_DWORD *)this + 10);
  pretinfo.cbStruct = 16;
  pretinfo.itagSequence = 0;
  pretinfo.columnidNextTagged = 0;
  if ( (*(int (__thiscall **)(int))(*(_DWORD *)v6 + 20))(v6)
    && ((v7 = (_DWORD *)(*(int (__thiscall **)(_DWORD))(**((_DWORD **)v15 + 4) + 20))(*((_DWORD *)v15 + 4)), v7[4] != 1)
     || (v8 = (CTransactionState *)v7[2]) == 0
      ? (isZombie = v7[3])
      : (isZombie = CTransactionState::isZombie(v8)),
        isZombie == 1) )
  {
    v10 = -2147418113;
  }
  else if ( a2 )
  {
    v11 = v15;
    if ( *((_DWORD *)v15 + 11) == 1 )
    {
      v12 = JetRetrieveColumn(
              *((_DWORD *)v15 + 5),
              *((_DWORD *)v15 + 6),
              *((_DWORD *)v15 + 7),
              a2,
              cbData,
              &pcbActual,
              *((_DWORD *)v15 + 9),
              &pretinfo);
      if ( !v12 || v12 == 1006 )
      {
        v13 = pcbActual;
        if ( cbData < pcbActual )
          v13 = cbData;
        *((_DWORD *)v11 + 10) += v13;
        v10 = 0;
        if ( a4 )
          *a4 = v13;
      }
      else
      {
        v10 = -2147467259;
      }
    }
    else
    {
      v10 = -2147287035;
    }
  }
  else
  {
    v10 = -2147287031;
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  return v10;
}

```

## disassembly

```asm
0x1001d4b0  mov     edi, edi
0x1001d4b2  push    ebp
0x1001d4b3  mov     ebp, esp
0x1001d4b5  push    0FFFFFFFFh
0x1001d4b7  push    offset ?Read@CImpISequentialStream@@UAGJPAXKPAK@Z_SEH
0x1001d4bc  mov     eax, large fs:0
0x1001d4c2  push    eax
0x1001d4c3  sub     esp, 28h
0x1001d4c6  mov     eax, ___security_cookie
0x1001d4cb  xor     eax, ebp
0x1001d4cd  mov     [ebp+var_10], eax
0x1001d4d0  push    ebx
0x1001d4d1  push    esi
0x1001d4d2  push    edi
0x1001d4d3  push    eax
0x1001d4d4  lea     eax, [ebp+var_C]
0x1001d4d7  mov     large fs:0, eax
0x1001d4dd  mov     eax, [ebp+arg_4]
0x1001d4e0  mov     ebx, [ebp+this]
0x1001d4e3  mov     [ebp+pvData], eax
0x1001d4e6  mov     eax, [ebp+arg_C]
0x1001d4e9  mov     [ebp+var_24], ebx
0x1001d4ec  mov     [ebp+var_34], eax
0x1001d4ef  mov     [ebp+pcbActual], 0
0x1001d4f6  mov     [ebp+var_2C], 0
0x1001d4fd  mov     [ebp+var_4], 0
0x1001d504  test    eax, eax
0x1001d506  jz      short loc_1001D50E
0x1001d508  mov     dword ptr [eax], 0
0x1001d50e  cmp     dword ptr [ebx+8], 1
0x1001d512  jnz     short loc_1001D51E
0x1001d514  mov     eax, 8000FFFFh
0x1001d519  jmp     loc_1001D61D
0x1001d51e  mov     edi, [ebx+10h]
0x1001d521  mov     eax, [edi]
0x1001d523  mov     esi, [eax+10h]
0x1001d526  mov     ecx, esi
0x1001d528  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d52e  mov     ecx, edi
0x1001d530  call    esi
0x1001d532  mov     esi, eax
0x1001d534  push    esi; lpCriticalSection
0x1001d535  mov     [ebp+var_2C], esi
0x1001d538  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d53e  mov     eax, [ebx+28h]
0x1001d541  mov     ebx, [ebx+10h]
0x1001d544  mov     [ebp+pretinfo.ibLongValue], eax
0x1001d547  mov     [ebp+pretinfo.cbStruct], 10h
0x1001d54e  mov     [ebp+pretinfo.itagSequence], 0
0x1001d555  mov     [ebp+pretinfo.columnidNextTagged], 0
0x1001d55c  mov     eax, [ebx]
0x1001d55e  mov     edi, [eax+14h]
0x1001d561  mov     ecx, edi
0x1001d563  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d569  mov     ecx, ebx
0x1001d56b  call    edi
0x1001d56d  test    eax, eax
0x1001d56f  jz      short loc_1001D5AB
0x1001d571  mov     ebx, [ebp+var_24]
0x1001d574  mov     ebx, [ebx+10h]
0x1001d577  mov     eax, [ebx]
0x1001d579  mov     edi, [eax+14h]
0x1001d57c  mov     ecx, edi
0x1001d57e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d584  mov     ecx, ebx
0x1001d586  call    edi
0x1001d588  cmp     dword ptr [eax+10h], 1
0x1001d58c  jnz     short loc_1001D59C
0x1001d58e  mov     ecx, [eax+8]; this
0x1001d591  test    ecx, ecx
0x1001d593  jz      short loc_1001D59C
0x1001d595  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1001d59a  jmp     short loc_1001D59F
0x1001d59c  mov     eax, [eax+0Ch]
0x1001d59f  cmp     eax, 1
0x1001d5a2  jnz     short loc_1001D5AB
0x1001d5a4  mov     ebx, 8000FFFFh
0x1001d5a9  jmp     short loc_1001D610
0x1001d5ab  mov     eax, [ebp+pvData]
0x1001d5ae  test    eax, eax
0x1001d5b0  jnz     short loc_1001D5B9
0x1001d5b2  mov     ebx, 80030009h
0x1001d5b7  jmp     short loc_1001D610
0x1001d5b9  mov     ebx, [ebp+var_24]
0x1001d5bc  cmp     dword ptr [ebx+2Ch], 1
0x1001d5c0  jz      short loc_1001D5C9
0x1001d5c2  mov     ebx, 80030005h
0x1001d5c7  jmp     short loc_1001D610
0x1001d5c9  mov     edi, [ebp+cbData]
0x1001d5cc  lea     ecx, [ebp+pretinfo]
0x1001d5cf  push    ecx; pretinfo
0x1001d5d0  push    dword ptr [ebx+24h]; grbit
0x1001d5d3  lea     ecx, [ebp+pcbActual]
0x1001d5d6  push    ecx; pcbActual
0x1001d5d7  push    edi; cbData
0x1001d5d8  push    eax; pvData
0x1001d5d9  push    dword ptr [ebx+1Ch]; columnid
0x1001d5dc  push    dword ptr [ebx+18h]; tableid
0x1001d5df  push    dword ptr [ebx+14h]; sesid
0x1001d5e2  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1001d5e8  test    eax, eax
0x1001d5ea  jz      short loc_1001D5FA
0x1001d5ec  cmp     eax, 3EEh
0x1001d5f1  jz      short loc_1001D5FA
0x1001d5f3  mov     ebx, 80004005h
0x1001d5f8  jmp     short loc_1001D610
0x1001d5fa  mov     ecx, [ebp+pcbActual]
0x1001d5fd  cmp     edi, ecx
0x1001d5ff  mov     edx, [ebp+var_34]
0x1001d602  cmovb   ecx, edi
0x1001d605  add     [ebx+28h], ecx
0x1001d608  xor     ebx, ebx
0x1001d60a  test    edx, edx
0x1001d60c  jz      short loc_1001D610
0x1001d60e  mov     [edx], ecx
0x1001d610  test    esi, esi
0x1001d612  jz      short loc_1001D61B
0x1001d614  push    esi; lpCriticalSection
0x1001d615  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001d61b  mov     eax, ebx
0x1001d61d  mov     ecx, [ebp+var_C]
0x1001d620  mov     large fs:0, ecx
0x1001d627  pop     ecx
0x1001d628  pop     edi
0x1001d629  pop     esi
0x1001d62a  pop     ebx
0x1001d62b  mov     ecx, [ebp+var_10]
0x1001d62e  xor     ecx, ebp; StackCookie
0x1001d630  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001d635  mov     esp, ebp
0x1001d637  pop     ebp
0x1001d638  retn    10h
0x1004e5b0  lea     ecx, [ebp+var_2C]; this
0x1004e5b3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e5bd  nop
0x1004e5be  nop
0x1004e5bf  mov     edx, [esp-4+arg_4]
0x1004e5c3  lea     eax, [edx+0Ch]
0x1004e5c6  mov     ecx, [edx-38h]
0x1004e5c9  xor     ecx, eax; StackCookie
0x1004e5cb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e5d0  mov     ecx, [edx-4]
0x1004e5d3  xor     ecx, eax; StackCookie
0x1004e5d5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e5da  mov     eax, offset stru_1004F9C0
0x1004e5df  jmp     ___CxxFrameHandler3
```
