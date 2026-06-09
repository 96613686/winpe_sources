# CHNetPortMappingProtocol::Delete(void)

- ea: `0x1800236c0`
- end: `0x180023915`
- name: `?Delete@CHNetPortMappingProtocol@@UEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(CHNetPortMappingProtocol *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800100f4`
- `0x1800236c0`
- `0x180024bd8`
- `0x180027fc4`
- `0x180028210`
- `0x180028c48`
- `0x18002ac5c`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180023733`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023733`
- `OLEAUT32!__imp_SysFreeString` at `0x180023902`
- `OLEAUT32!__imp_SysFreeString` at `0x180023902`

## string_xrefs

- `0x1800236fb`: `Protocol`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingProtocol::Delete(CHNetPortMappingProtocol *this)
{
  bool v2; // zf
  unsigned __int16 *v3; // rsi
  unsigned int v4; // ebx
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  CHNetPortMappingBinding *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v13; // [rsp+40h] [rbp-10h] BYREF
  int v14; // [rsp+80h] [rbp+30h] BYREF
  struct IWbemClassObject *v15; // [rsp+88h] [rbp+38h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h] BYREF
  CHNetPortMappingBinding *v17; // [rsp+98h] [rbp+48h] BYREF

  v2 = *((_BYTE *)this + 88) == 1;
  v3 = 0;
  v16 = 0;
  v15 = 0;
  v13 = 0;
  v14 = 0;
  if ( v2 )
  {
    v4 = -2147024891;
  }
  else
  {
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 10);
    v17 = 0;
    v4 = BuildEscapedQuotedEqualsString((unsigned __int16 **)&v17, L"Protocol", v5);
    if ( !v4 )
    {
      v4 = BuildSelectQueryBstr(&v13, v6, L"HNet_ConnectionPortMapping2", (const unsigned __int16 *)v17);
      operator delete[](v17);
      v3 = v13;
      if ( !v4 )
      {
        v7 = *((_QWORD *)this + 9);
        v8 = *((_QWORD *)this + 12);
        v16 = 0;
        (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *, __int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 160LL))(
          v7,
          v8,
          v13,
          48,
          0,
          &v16);
        do
        {
          v15 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, int *))(*(_QWORD *)v16 + 32LL))(
                 v16,
                 0xFFFFFFFFLL,
                 1,
                 &v15,
                 &v14) < 0
            || v14 != 1 )
          {
            break;
          }
          v17 = 0;
          if ( (int)ATL::CComObject<CHNetPortMappingBinding>::CreateInstance(&v17) >= 0 )
          {
            v9 = v17;
            (*(void (__fastcall **)(CHNetPortMappingBinding *))(*(_QWORD *)v17 + 8LL))(v17);
            CHNetPortMappingBinding::Initialize(v9, *((struct IWbemServices **)this + 9), v15);
            (*(void (__fastcall **)(CHNetPortMappingBinding *, _QWORD))(*(_QWORD *)v9 + 48LL))(v9, 0);
            (*(void (__fastcall **)(CHNetPortMappingBinding *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
        }
        while ( v14 == 1 );
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 9) + 128LL))(
               *((_QWORD *)this + 9),
               *((_QWORD *)this + 10),
               0,
               0,
               0);
        if ( !v4 )
        {
          v10 = *((_QWORD *)this + 9);
          v11 = *((_QWORD *)this + 12);
          v16 = 0;
          (*(void (__fastcall **)(__int64, __int64, unsigned __int16 *, __int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 160LL))(
            v10,
            v11,
            v3,
            48,
            0,
            &v16);
          do
          {
            v15 = 0;
            if ( (*(int (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, int *))(*(_QWORD *)v16 + 32LL))(
                   v16,
                   0xFFFFFFFFLL,
                   1,
                   &v15,
                   &v14) < 0 )
              break;
            if ( v14 != 1 )
              break;
            DeleteWmiInstance(*((struct IWbemServices **)this + 9), v15);
            ((void (__fastcall *)(struct IWbemClassObject *))v15->lpVtbl->Release)(v15);
          }
          while ( v14 == 1 );
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v4 = 0;
          UpdateService(0x87u);
        }
      }
    }
  }
  SysFreeString(v3);
  return v4;
}

```

## disassembly

```asm
0x1800236c0  push    rbp
0x1800236c2  push    rbx
0x1800236c3  push    rsi
0x1800236c4  push    rdi
0x1800236c5  push    r14
0x1800236c7  mov     rbp, rsp
0x1800236ca  sub     rsp, 50h
0x1800236ce  xor     r14d, r14d
0x1800236d1  mov     rdi, rcx
0x1800236d4  cmp     byte ptr [rcx+58h], 1
0x1800236d8  mov     esi, r14d
0x1800236db  mov     [rbp+arg_10], r14
0x1800236df  mov     [rbp+arg_8], r14
0x1800236e3  mov     [rbp+var_10], r14
0x1800236e7  mov     [rbp+arg_0], r14d
0x1800236eb  jnz     short loc_1800236F7
0x1800236ed  mov     ebx, 80070005h
0x1800236f2  jmp     loc_1800238FF
0x1800236f7  mov     r8, [rcx+50h]; unsigned __int16 *
0x1800236fb  lea     rdx, ?c_wszProtocol@@3QBGB; "Protocol"
0x180023702  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x180023706  mov     [rbp+arg_18], r14
0x18002370a  call    ?BuildEscapedQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildEscapedQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x18002370f  mov     ebx, eax
0x180023711  test    eax, eax
0x180023713  jnz     loc_1800238FF
0x180023719  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x18002371d  lea     r8, ?c_wszHnetConnectionPortMapping@@3QBGB; "HNet_ConnectionPortMapping2"
0x180023724  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180023728  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x18002372d  mov     rcx, [rbp+arg_18]
0x180023731  mov     ebx, eax
0x180023733  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180023739  mov     rsi, [rbp+var_10]
0x18002373d  test    ebx, ebx
0x18002373f  jnz     loc_1800238FF
0x180023745  mov     rcx, [rdi+48h]
0x180023749  lea     rdx, [rbp+arg_10]
0x18002374d  mov     [rsp+50h+var_28], rdx
0x180023752  lea     r9d, [rbx+30h]
0x180023756  mov     rdx, [rdi+60h]
0x18002375a  mov     r8, rsi
0x18002375d  mov     [rbp+arg_10], r14
0x180023761  mov     rax, [rcx]
0x180023764  mov     [rsp+50h+var_30], r14
0x180023769  mov     rax, [rax+0A0h]
0x180023770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023775  mov     rcx, [rbp+arg_10]
0x180023779  lea     rdx, [rbp+arg_0]
0x18002377d  mov     [rbp+arg_8], r14
0x180023781  lea     r9, [rbp+arg_8]
0x180023785  mov     [rsp+50h+var_30], rdx
0x18002378a  mov     r8d, 1
0x180023790  or      edx, 0FFFFFFFFh
0x180023793  mov     rax, [rcx]
0x180023796  mov     rax, [rax+20h]
0x18002379a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002379f  test    eax, eax
0x1800237a1  js      short loc_18002381B
0x1800237a3  mov     eax, [rbp+arg_0]
0x1800237a6  cmp     eax, 1
0x1800237a9  jnz     short loc_18002381B
0x1800237ab  lea     rcx, [rbp+arg_18]
0x1800237af  mov     [rbp+arg_18], r14
0x1800237b3  call    ?CreateInstance@?$CComObject@VCHNetPortMappingBinding@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetPortMappingBinding>::CreateInstance(ATL::CComObject<CHNetPortMappingBinding> * *)
0x1800237b8  test    eax, eax
0x1800237ba  js      short loc_1800237FF
0x1800237bc  mov     rbx, [rbp+arg_18]
0x1800237c0  mov     rcx, rbx
0x1800237c3  mov     rax, [rbx]
0x1800237c6  mov     rax, [rax+8]
0x1800237ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237cf  mov     r8, [rbp+arg_8]; struct IWbemClassObject *
0x1800237d3  mov     rcx, rbx; this
0x1800237d6  mov     rdx, [rdi+48h]; struct IWbemServices *
0x1800237da  call    ?Initialize@CHNetPortMappingBinding@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CHNetPortMappingBinding::Initialize(IWbemServices *,IWbemClassObject *)
0x1800237df  mov     rax, [rbx]
0x1800237e2  xor     edx, edx
0x1800237e4  mov     rcx, rbx
0x1800237e7  mov     rax, [rax+30h]
0x1800237eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f0  mov     rax, [rbx]
0x1800237f3  mov     rcx, rbx
0x1800237f6  mov     rax, [rax+10h]
0x1800237fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237ff  mov     rcx, [rbp+arg_8]
0x180023803  mov     rax, [rcx]
0x180023806  mov     rax, [rax+10h]
0x18002380a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002380f  mov     eax, [rbp+arg_0]
0x180023812  cmp     eax, 1
0x180023815  jz      loc_180023775
0x18002381b  mov     rcx, [rbp+arg_10]
0x18002381f  mov     rax, [rcx]
0x180023822  mov     rax, [rax+10h]
0x180023826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002382b  mov     rcx, [rdi+48h]
0x18002382f  xor     r9d, r9d
0x180023832  mov     rdx, [rdi+50h]
0x180023836  xor     r8d, r8d
0x180023839  mov     [rsp+50h+var_30], r14
0x18002383e  mov     rax, [rcx]
0x180023841  mov     rax, [rax+80h]
0x180023848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002384d  mov     ebx, eax
0x18002384f  test    eax, eax
0x180023851  jnz     loc_1800238FF
0x180023857  mov     rcx, [rdi+48h]
0x18002385b  lea     rdx, [rbp+arg_10]
0x18002385f  mov     [rsp+50h+var_28], rdx
0x180023864  lea     r9d, [rbx+30h]
0x180023868  mov     rdx, [rdi+60h]
0x18002386c  mov     r8, rsi
0x18002386f  mov     [rbp+arg_10], r14
0x180023873  mov     rax, [rcx]
0x180023876  mov     [rsp+50h+var_30], r14
0x18002387b  mov     rax, [rax+0A0h]
0x180023882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023887  mov     rcx, [rbp+arg_10]
0x18002388b  lea     rdx, [rbp+arg_0]
0x18002388f  mov     [rbp+arg_8], r14
0x180023893  lea     r9, [rbp+arg_8]
0x180023897  mov     [rsp+50h+var_30], rdx
0x18002389c  mov     r8d, 1
0x1800238a2  or      edx, 0FFFFFFFFh
0x1800238a5  mov     rax, [rcx]
0x1800238a8  mov     rax, [rax+20h]
0x1800238ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238b1  test    eax, eax
0x1800238b3  js      short loc_1800238E2
0x1800238b5  mov     eax, [rbp+arg_0]
0x1800238b8  cmp     eax, 1
0x1800238bb  jnz     short loc_1800238E2
0x1800238bd  mov     rdx, [rbp+arg_8]; struct IWbemClassObject *
0x1800238c1  mov     rcx, [rdi+48h]; struct IWbemServices *
0x1800238c5  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x1800238ca  mov     rcx, [rbp+arg_8]
0x1800238ce  mov     rax, [rcx]
0x1800238d1  mov     rax, [rax+10h]
0x1800238d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238da  mov     eax, [rbp+arg_0]
0x1800238dd  cmp     eax, 1
0x1800238e0  jz      short loc_180023887
0x1800238e2  mov     rcx, [rbp+arg_10]
0x1800238e6  mov     rax, [rcx]
0x1800238e9  mov     rax, [rax+10h]
0x1800238ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238f2  mov     ecx, 87h; dwControl
0x1800238f7  mov     ebx, r14d
0x1800238fa  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x1800238ff  mov     rcx, rsi; bstrString
0x180023902  call    cs:__imp_SysFreeString
0x180023908  mov     eax, ebx
0x18002390a  add     rsp, 50h
0x18002390e  pop     r14
0x180023910  pop     rdi
0x180023911  pop     rsi
0x180023912  pop     rbx
0x180023913  pop     rbp
0x180023914  retn
```
