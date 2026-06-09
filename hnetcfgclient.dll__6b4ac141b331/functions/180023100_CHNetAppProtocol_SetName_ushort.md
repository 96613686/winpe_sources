# CHNetAppProtocol::SetName(ushort *)

- ea: `0x180023100`
- end: `0x180023263`
- name: `?SetName@CHNetAppProtocol@@UEAAJPEAG@Z`
- size: `355`
- prototype: `int(CHNetAppProtocol *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005698`
- `0x180023100`
- `0x180029a3c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800231b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800231b7`
- `OLEAUT32!__imp_VariantInit` at `0x18002314b`
- `OLEAUT32!__imp_VariantInit` at `0x1800231a6`
- `OLEAUT32!__imp_VariantInit` at `0x18002314b`
- `OLEAUT32!__imp_VariantInit` at `0x1800231a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800231fd`
- `OLEAUT32!__imp_VariantClear` at `0x1800231fd`

## pseudocode

```c
__int64 __fastcall CHNetAppProtocol::SetName(CHNetAppProtocol *this, size_t *a2)
{
  unsigned int WmiObjectFromPath; // ebx
  struct IWbemClassObject *v6; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v8[256]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( *((_BYTE *)this + 80) == 1 )
  {
    WmiObjectFromPath = -2147024891;
  }
  else
  {
    WmiObjectFromPath = 0;
    if ( !a2 )
      WmiObjectFromPath = -2147024809;
  }
  StringCchCopyW(v8, 0x100u, a2);
  if ( !WmiObjectFromPath )
  {
    WmiObjectFromPath = GetWmiObjectFromPath(
                          *((struct IWbemServices **)this + 8),
                          *((unsigned __int16 **)this + 9),
                          &v6);
    if ( !WmiObjectFromPath )
    {
      VariantInit(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)a2);
      if ( pvarg.llVal )
      {
        WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v6->lpVtbl->Put)(
                              v6,
                              L"Name",
                              0,
                              &pvarg,
                              0);
        VariantClear(&pvarg);
        if ( !WmiObjectFromPath )
          WmiObjectFromPath = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 112LL))(
                                *((_QWORD *)this + 8),
                                v6,
                                1,
                                0,
                                0);
      }
      else
      {
        WmiObjectFromPath = -2147024882;
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v6->lpVtbl->Release)(v6);
    }
  }
  return WmiObjectFromPath;
}

```

## disassembly

```asm
0x180023100  mov     [rsp-8+arg_10], rbx
0x180023105  push    rbp
0x180023106  push    rsi
0x180023107  push    rdi
0x180023108  lea     rbp, [rsp-160h]
0x180023110  sub     rsp, 260h
0x180023117  mov     rax, cs:__security_cookie
0x18002311e  xor     rax, rsp
0x180023121  mov     [rbp+170h+var_20], rax
0x180023128  mov     rsi, rcx
0x18002312b  mov     [rsp+270h+var_240], 0
0x180023134  xorps   xmm0, xmm0
0x180023137  lea     rcx, [rsp+270h+pvarg]; pvarg
0x18002313c  xor     eax, eax
0x18002313e  mov     rdi, rdx
0x180023141  movups  xmmword ptr [rsp+270h+pvarg], xmm0
0x180023146  mov     qword ptr [rsp+270h+pvarg+10h], rax
0x18002314b  call    cs:__imp_VariantInit
0x180023151  cmp     byte ptr [rsi+50h], 1
0x180023155  jnz     short loc_18002315E
0x180023157  mov     ebx, 80070005h
0x18002315c  jmp     short loc_18002316B
0x18002315e  xor     ebx, ebx
0x180023160  mov     eax, 80070057h
0x180023165  test    rdi, rdi
0x180023168  cmovz   ebx, eax
0x18002316b  mov     r8, rdi; unsigned __int16 *
0x18002316e  lea     rcx, [rsp+270h+var_220]; unsigned __int16 *
0x180023173  mov     edx, 100h; unsigned __int64
0x180023178  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002317d  test    ebx, ebx
0x18002317f  jnz     loc_18002323F
0x180023185  mov     rdx, [rsi+48h]; unsigned __int16 *
0x180023189  lea     r8, [rsp+270h+var_240]; struct IWbemClassObject **
0x18002318e  mov     rcx, [rsi+40h]; struct IWbemServices *
0x180023192  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180023197  mov     ebx, eax
0x180023199  test    eax, eax
0x18002319b  jnz     loc_18002323F
0x1800231a1  lea     rcx, [rsp+270h+pvarg]; pvarg
0x1800231a6  call    cs:__imp_VariantInit
0x1800231ac  lea     eax, [rbx+8]
0x1800231af  mov     rcx, rdi; psz
0x1800231b2  mov     word ptr [rsp+270h+pvarg], ax
0x1800231b7  call    cs:__imp_SysAllocString
0x1800231bd  mov     qword ptr [rsp+270h+pvarg+8], rax
0x1800231c2  test    rax, rax
0x1800231c5  jnz     short loc_1800231CE
0x1800231c7  mov     ebx, 8007000Eh
0x1800231cc  jmp     short loc_18002322E
0x1800231ce  mov     rcx, [rsp+270h+var_240]
0x1800231d3  lea     r9, [rsp+270h+pvarg]
0x1800231d8  xor     r8d, r8d
0x1800231db  mov     dword ptr [rsp+270h+var_250], 0
0x1800231e3  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x1800231ea  mov     rax, [rcx]
0x1800231ed  mov     rax, [rax+28h]
0x1800231f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231f6  lea     rcx, [rsp+270h+pvarg]; pvarg
0x1800231fb  mov     ebx, eax
0x1800231fd  call    cs:__imp_VariantClear
0x180023203  test    ebx, ebx
0x180023205  jnz     short loc_18002322E
0x180023207  mov     rcx, [rsi+40h]
0x18002320b  lea     r8d, [rbx+1]
0x18002320f  mov     rdx, [rsp+270h+var_240]
0x180023214  xor     r9d, r9d
0x180023217  mov     [rsp+270h+var_250], 0
0x180023220  mov     rax, [rcx]
0x180023223  mov     rax, [rax+70h]
0x180023227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002322c  mov     ebx, eax
0x18002322e  mov     rcx, [rsp+270h+var_240]
0x180023233  mov     rax, [rcx]
0x180023236  mov     rax, [rax+10h]
0x18002323a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002323f  mov     eax, ebx
0x180023241  mov     rcx, [rbp+170h+var_20]
0x180023248  xor     rcx, rsp; StackCookie
0x18002324b  call    __security_check_cookie
0x180023250  mov     rbx, [rsp+270h+arg_10]
0x180023258  add     rsp, 260h
0x18002325f  pop     rdi
0x180023260  pop     rsi
0x180023261  pop     rbp
0x180023262  retn
```
