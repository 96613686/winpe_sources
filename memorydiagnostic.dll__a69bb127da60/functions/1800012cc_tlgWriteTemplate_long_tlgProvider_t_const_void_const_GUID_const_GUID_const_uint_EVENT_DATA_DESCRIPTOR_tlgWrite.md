# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800012cc`
- end: `0x18000138c`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800047bc`
- `0x180004854`
- `0x180004a54`
- `0x180004aec`

## callees

- `0x1800012cc`
- `0x180001a7c`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6,
        __int64 a7)
{
  int *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-68h] BYREF
  int *v13; // [rsp+50h] [rbp-48h]
  int v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+5Ch] [rbp-3Ch]
  __int64 v16; // [rsp+60h] [rbp-38h]
  __int64 v17; // [rsp+68h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v19 = 8;
  v17 = 8;
  v8 = *a5;
  if ( *a5 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &dword_180025214;
    v10 = 2;
  }
  v14 = v10;
  v13 = v8;
  v15 = 0;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           5,
           v12);
}

```

## disassembly

```asm
0x1800012cc  mov     r11, rsp
0x1800012cf  sub     rsp, 98h
0x1800012d6  mov     rax, cs:__security_cookie
0x1800012dd  xor     rax, rsp
0x1800012e0  mov     [rsp+98h+var_18], rax
0x1800012e8  mov     rax, [rsp+98h+arg_30]
0x1800012f0  mov     r10, rcx
0x1800012f3  mov     [r11-28h], rax
0x1800012f7  xor     r8d, r8d
0x1800012fa  mov     rax, [rsp+98h+arg_28]
0x180001302  mov     [r11-38h], rax
0x180001306  mov     rax, [rsp+98h+arg_20]
0x18000130e  mov     qword ptr [r11-20h], 8
0x180001316  mov     qword ptr [r11-30h], 8
0x18000131e  mov     rcx, [rax]
0x180001321  test    rcx, rcx
0x180001324  jz      short loc_18000133D
0x180001326  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000132a  inc     rax
0x18000132d  cmp     [rcx+rax*2], r8w
0x180001332  jnz     short loc_18000132A
0x180001334  lea     eax, ds:2[rax*2]
0x18000133b  jmp     short loc_180001349
0x18000133d  lea     rcx, dword_180025214
0x180001344  mov     eax, 2
0x180001349  mov     [rsp+98h+var_40], eax
0x18000134d  xor     r9d, r9d
0x180001350  lea     rax, [rsp+98h+var_68]
0x180001355  mov     [rsp+98h+var_48], rcx
0x18000135a  mov     [rsp+98h+var_70], rax
0x18000135f  mov     rcx, r10
0x180001362  mov     [rsp+98h+var_78], 5
0x18000136a  mov     [rsp+98h+var_3C], r8d
0x18000136f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001374  mov     rcx, [rsp+98h+var_18]
0x18000137c  xor     rcx, rsp; StackCookie
0x18000137f  call    __security_check_cookie
0x180001384  add     rsp, 98h
0x18000138b  retn
```
