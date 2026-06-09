# ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)

- ea: `0x180031000`
- end: `0x1800312b0`
- name: `?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z`
- size: `688`
- prototype: `int(struct ISimpleTableDispenser *, const unsigned __int16 *, struct _GUID *, struct _GUID *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018620`
- `0x18001a924`
- `0x18001b664`
- `0x18001bf9c`

## callees

- `0x180030968`
- `0x180031000`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180031191`
- `msvcrt!_wcsicmp` at `0x180031191`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031065`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031065`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800310c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800310c3`

## pseudocode

```c
__int64 __fastcall ResolveAppIdFromName(
        struct ISimpleTableDispenser *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  HRESULT Instance; // ebx
  int v9; // eax
  struct _GUID *v10; // [rsp+50h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-8h]
  struct ISimpleTableDispenser *ppv; // [rsp+80h] [rbp+20h] BYREF
  __int64 v13; // [rsp+88h] [rbp+28h] BYREF

  ppv = a1;
  v13 = 0;
  v10 = 0;
  String1 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = GUID_NULL;
  if ( *a2 == 123 )
  {
    if ( CLSIDFromString(a2, a3) >= 0 )
    {
      if ( a4 )
        return GetPartitionFromAppId(ppv, a3, a4);
      else
        return 0;
    }
    a1 = ppv;
  }
  if ( a1 )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)a1 + 8LL))(a1);
LABEL_12:
    Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, const struct _GUID *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 didCOMSERVICES,
                 &TID_APPLICATION,
                 0,
                 0,
                 1,
                 1,
                 &v13);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
      if ( Instance >= 0 )
      {
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
          Instance = v9;
          if ( v9 < 0 )
            break;
          Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, 1, 0);
          if ( Instance < 0 )
            goto LABEL_27;
          if ( !String1 )
          {
            Instance = -2147418113;
            goto LABEL_27;
          }
          if ( !_wcsicmp(String1, a2) )
          {
            if ( memcmp_0(a3, &GUID_NULL, 0x10u) )
            {
              Instance = -2146368420;
              goto LABEL_27;
            }
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct _GUID **))(*(_QWORD *)v13 + 64LL))(
                         v13,
                         0,
                         0,
                         0,
                         &v10);
            if ( Instance < 0 )
              goto LABEL_27;
            *a3 = *v10;
            if ( a4 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, 41, 0);
              if ( Instance < 0 )
                goto LABEL_27;
              *a4 = *v10;
            }
          }
        }
        if ( v9 == -2146367487 )
          Instance = memcmp_0(a3, &GUID_NULL, 0x10u) == 0 ? 0x80110809 : 0;
      }
    }
    goto LABEL_27;
  }
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 0x17u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
    goto LABEL_12;
LABEL_27:
  if ( ppv )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180031000  mov     [rsp-18h+arg_10], rbx
0x180031005  mov     [rsp-18h+arg_18], rsi
0x18003100a  mov     [rsp-18h+arg_0], rcx
0x18003100f  push    rbp
0x180031010  push    rdi
0x180031011  push    r14
0x180031013  mov     rbp, rsp
0x180031016  sub     rsp, 60h
0x18003101a  mov     [rbp+arg_8], 0
0x180031022  mov     rsi, r9
0x180031025  mov     [rbp+var_10], 0
0x18003102d  mov     rdi, r8
0x180031030  mov     [rbp+String1], 0
0x180031038  mov     r14, rdx
0x18003103b  test    rdx, rdx
0x18003103e  jz      loc_180031296
0x180031044  test    r8, r8
0x180031047  jz      loc_180031296
0x18003104d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180031054  movdqu  xmmword ptr [r8], xmm0
0x180031059  cmp     word ptr [rdx], 7Bh ; '{'
0x18003105d  jnz     short loc_180031093
0x18003105f  mov     rdx, r8; pclsid
0x180031062  mov     rcx, r14; lpsz
0x180031065  call    cs:__imp_CLSIDFromString
0x18003106b  test    eax, eax
0x18003106d  js      short loc_18003108F
0x18003106f  test    rsi, rsi
0x180031072  jnz     short loc_18003107B
0x180031074  xor     eax, eax
0x180031076  jmp     loc_18003129B
0x18003107b  mov     rcx, [rbp+arg_0]; struct ISimpleTableDispenser *
0x18003107f  mov     r8, rsi; struct _GUID *
0x180031082  mov     rdx, rdi; struct _GUID *
0x180031085  call    ?GetPartitionFromAppId@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAU2@@Z; GetPartitionFromAppId(ISimpleTableDispenser *,_GUID const &,_GUID *)
0x18003108a  jmp     loc_18003129B
0x18003108f  mov     rcx, [rbp+arg_0]
0x180031093  test    rcx, rcx
0x180031096  jz      short loc_1800310A6
0x180031098  mov     rax, [rcx]
0x18003109b  mov     rax, [rax+8]
0x18003109f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310a4  jmp     short loc_1800310D3
0x1800310a6  xor     edx, edx; pUnkOuter
0x1800310a8  lea     rax, [rbp+arg_0]
0x1800310ac  lea     r9, IID_ISimpleTableDispenser; riid
0x1800310b3  mov     [rsp+60h+ppv], rax; ppv
0x1800310b8  lea     rcx, CLSID_STDispenser; rclsid
0x1800310bf  lea     r8d, [rdx+17h]; dwClsContext
0x1800310c3  call    cs:__imp_CoCreateInstance
0x1800310c9  mov     ebx, eax
0x1800310cb  test    eax, eax
0x1800310cd  js      loc_180031260
0x1800310d3  mov     rcx, [rbp+arg_0]
0x1800310d7  lea     rdx, [rbp+arg_8]
0x1800310db  mov     [rsp+60h+var_28], rdx
0x1800310e0  lea     r8, TID_APPLICATION
0x1800310e7  mov     [rsp+60h+var_30], 1
0x1800310ef  lea     rdx, didCOMSERVICES
0x1800310f6  mov     [rsp+60h+var_38], 1
0x1800310fe  xor     r9d, r9d
0x180031101  mov     rax, [rcx]
0x180031104  mov     [rsp+60h+ppv], 0
0x18003110d  mov     rax, [rax+18h]
0x180031111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031116  mov     ebx, eax
0x180031118  test    eax, eax
0x18003111a  js      loc_180031260
0x180031120  mov     rcx, [rbp+arg_8]
0x180031124  mov     rax, [rcx]
0x180031127  mov     rax, [rax+18h]
0x18003112b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031130  mov     ebx, eax
0x180031132  test    eax, eax
0x180031134  js      loc_180031260
0x18003113a  mov     rcx, [rbp+arg_8]
0x18003113e  mov     rax, [rcx]
0x180031141  mov     rax, [rax+28h]
0x180031145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003114a  mov     ebx, eax
0x18003114c  test    eax, eax
0x18003114e  js      loc_180031238
0x180031154  mov     rcx, [rbp+arg_8]
0x180031158  lea     rdx, [rbp+String1]
0x18003115c  xor     r9d, r9d
0x18003115f  mov     [rsp+60h+ppv], rdx
0x180031164  xor     r8d, r8d
0x180031167  mov     rax, [rcx]
0x18003116a  lea     edx, [r9+1]
0x18003116e  mov     rax, [rax+40h]
0x180031172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031177  mov     ebx, eax
0x180031179  test    eax, eax
0x18003117b  js      loc_180031260
0x180031181  mov     rcx, [rbp+String1]; String1
0x180031185  test    rcx, rcx
0x180031188  jz      loc_180031231
0x18003118e  mov     rdx, r14; String2
0x180031191  call    cs:__imp__wcsicmp
0x180031197  test    eax, eax
0x180031199  jnz     short loc_18003113A
0x18003119b  lea     r8d, [rax+10h]; Size
0x18003119f  mov     rcx, rdi; Buf1
0x1800311a2  lea     rdx, GUID_NULL; Buf2
0x1800311a9  call    memcmp_0
0x1800311ae  test    eax, eax
0x1800311b0  jnz     short loc_18003122A
0x1800311b2  mov     rcx, [rbp+arg_8]
0x1800311b6  lea     rdx, [rbp+var_10]
0x1800311ba  mov     [rsp+60h+ppv], rdx
0x1800311bf  xor     r9d, r9d
0x1800311c2  xor     r8d, r8d
0x1800311c5  xor     edx, edx
0x1800311c7  mov     rax, [rcx]
0x1800311ca  mov     rax, [rax+40h]
0x1800311ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311d3  mov     ebx, eax
0x1800311d5  test    eax, eax
0x1800311d7  js      loc_180031260
0x1800311dd  mov     rax, [rbp+var_10]
0x1800311e1  movups  xmm0, xmmword ptr [rax]
0x1800311e4  movdqu  xmmword ptr [rdi], xmm0
0x1800311e8  test    rsi, rsi
0x1800311eb  jz      loc_18003113A
0x1800311f1  mov     rcx, [rbp+arg_8]
0x1800311f5  lea     rdx, [rbp+var_10]
0x1800311f9  xor     r9d, r9d
0x1800311fc  mov     [rsp+60h+ppv], rdx
0x180031201  xor     r8d, r8d
0x180031204  mov     rax, [rcx]
0x180031207  lea     edx, [r9+29h]
0x18003120b  mov     rax, [rax+40h]
0x18003120f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031214  mov     ebx, eax
0x180031216  test    eax, eax
0x180031218  js      short loc_180031260
0x18003121a  mov     rax, [rbp+var_10]
0x18003121e  movups  xmm0, xmmword ptr [rax]
0x180031221  movdqu  xmmword ptr [rsi], xmm0
0x180031225  jmp     loc_18003113A
0x18003122a  mov     ebx, 8011045Ch
0x18003122f  jmp     short loc_180031260
0x180031231  mov     ebx, 8000FFFFh
0x180031236  jmp     short loc_180031260
0x180031238  cmp     eax, 80110801h
0x18003123d  jnz     short loc_180031260
0x18003123f  mov     r8d, 10h; Size
0x180031245  lea     rdx, GUID_NULL; Buf2
0x18003124c  mov     rcx, rdi; Buf1
0x18003124f  call    memcmp_0
0x180031254  neg     eax
0x180031256  sbb     ebx, ebx
0x180031258  not     ebx
0x18003125a  and     ebx, 80110809h
0x180031260  mov     rcx, [rbp+arg_0]
0x180031264  test    rcx, rcx
0x180031267  jz      short loc_18003127D
0x180031269  mov     rax, [rcx]
0x18003126c  mov     rax, [rax+10h]
0x180031270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031275  mov     [rbp+arg_0], 0
0x18003127d  mov     rcx, [rbp+arg_8]
0x180031281  test    rcx, rcx
0x180031284  jz      short loc_180031292
0x180031286  mov     rax, [rcx]
0x180031289  mov     rax, [rax+10h]
0x18003128d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031292  mov     eax, ebx
0x180031294  jmp     short loc_18003129B
0x180031296  mov     eax, 80004003h
0x18003129b  lea     r11, [rsp+60h+var_s0]
0x1800312a0  mov     rbx, [r11+30h]
0x1800312a4  mov     rsi, [r11+38h]
0x1800312a8  mov     rsp, r11
0x1800312ab  pop     r14
0x1800312ad  pop     rdi
0x1800312ae  pop     rbp
0x1800312af  retn
```
