# DdmDevice::AcceptNewLink(RasObjPtr<DdmConnection> &)

- ea: `0x18002f8e0`
- end: `0x18002fb37`
- name: `?AcceptNewLink@DdmDevice@@UEAAHAEAV?$RasObjPtr@VDdmConnection@@@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(DdmDevice *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007c50`
- `0x18002f8e0`
- `0x180033fb0`
- `0x180034168`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18002f9de`
- `msvcrt!_itow_s` at `0x18002f9de`
- `KERNEL32!LeaveCriticalSection` at `0x18002faa2`
- `KERNEL32!LeaveCriticalSection` at `0x18002fb05`
- `KERNEL32!LeaveCriticalSection` at `0x18002faa2`
- `KERNEL32!LeaveCriticalSection` at `0x18002fb05`
- `KERNEL32!EnterCriticalSection` at `0x18002f962`
- `KERNEL32!EnterCriticalSection` at `0x18002f962`

## string_xrefs

- `0x18002fa01`: `AcceptNewLink: Skipping version 1 Admin Dll callback for IKEv2 connection`

## pseudocode

```c
__int64 __fastcall DdmDevice::AcceptNewLink(DdmDevice *this, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  unsigned int v5; // edi
  unsigned int v6; // esi
  int v7; // ecx
  int v8; // r13d
  char *v9; // r15
  __int64 v10; // r14
  int v11; // ecx
  unsigned int i; // ebx
  void (__fastcall *v14)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *); // rax
  int v15; // [rsp+30h] [rbp-D0h]
  struct _RAS_PORT_1 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+90h] [rbp-70h] BYREF
  struct _RAS_PORT_0 v18; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Buffer[2]; // [rsp+230h] [rbp+130h] BYREF
  __int128 v20; // [rsp+234h] [rbp+134h]
  __int128 v21; // [rsp+244h] [rbp+144h]
  int v22; // [rsp+254h] [rbp+154h]

  memset_0(&v18, 0, sizeof(v18));
  memset_0(&v16, 0, sizeof(v16));
  v4 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a2 + 16LL);
  *(_DWORD *)Buffer = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v17 = 0;
  EnterCriticalSection(v4);
  v5 = 0;
  v6 = 1;
  v7 = *(_DWORD *)(*(_QWORD *)a2 + 80LL) & 0x80;
  v8 = 1;
  v15 = v7;
  if ( dword_1800C8568 )
  {
    while ( 1 )
    {
      v9 = (char *)qword_1800C8560;
      v10 = 168LL * v5;
      if ( v7 && *((_BYTE *)qword_1800C8560 + v10 + 8) == 1 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          Buffer[0] = 0;
          if ( this )
          {
            v11 = *((_DWORD *)this + 24);
            if ( v11 != -1 )
              _itow_s(v11, Buffer, 0x14u, 10);
          }
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)L"AcceptNewLink: Skipping version 1 Admin Dll callback for IKEv2 connection",
              (unsigned int)&v17,
              0,
              (__int64)Buffer);
        }
      }
      else if ( *(_QWORD *)((char *)qword_1800C8560 + v10 + 72) )
      {
        if ( v8 )
        {
          if ( DdmDevice::GetRasPortData(this, &v18) || DdmDevice::GetRasPortData(this, &v16) )
          {
            (*(void (__fastcall **)(DdmDevice *))(*(_QWORD *)this + 176LL))(this);
            LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a2 + 16LL));
            return 0;
          }
          v8 = 0;
          *((_DWORD *)this + 33) &= ~0x20u;
        }
        if ( !(*(unsigned int (__fastcall **)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *))&v9[v10 + 72])(&v18, &v16) )
        {
          (*(void (__fastcall **)(DdmDevice *))(*(_QWORD *)this + 176LL))(this);
          for ( i = 0; i < v5; ++i )
          {
            v14 = (void (__fastcall *)(struct _RAS_PORT_0 *, struct _RAS_PORT_1 *))*((_QWORD *)qword_1800C8560
                                                                                   + 21 * i
                                                                                   + 13);
            if ( v14 )
              v14(&v18, &v16);
          }
          v6 = 0;
          goto LABEL_25;
        }
      }
      if ( ++v5 >= dword_1800C8568 )
        break;
      v7 = v15;
    }
  }
  *((_DWORD *)this + 33) |= 0x20u;
LABEL_25:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a2 + 16LL));
  return v6;
}

```

## disassembly

```asm
0x18002f8e0  mov     [rsp-8+arg_10], rbx
0x18002f8e5  push    rbp
0x18002f8e6  push    rsi
0x18002f8e7  push    rdi
0x18002f8e8  push    r12
0x18002f8ea  push    r13
0x18002f8ec  push    r14
0x18002f8ee  push    r15
0x18002f8f0  lea     rbp, [rsp-160h]
0x18002f8f8  sub     rsp, 260h
0x18002f8ff  mov     rax, cs:__security_cookie
0x18002f906  xor     rax, rsp
0x18002f909  mov     [rbp+190h+var_38], rax
0x18002f910  mov     r12, rdx
0x18002f913  mov     rbx, rcx
0x18002f916  xor     edx, edx; Val
0x18002f918  lea     rcx, [rbp+190h+var_1F0]; void *
0x18002f91c  mov     r8d, 188h; Size
0x18002f922  call    memset_0
0x18002f927  xor     edx, edx; Val
0x18002f929  lea     rcx, [rsp+290h+var_250]; void *
0x18002f92e  lea     r8d, [rdx+48h]; Size
0x18002f932  call    memset_0
0x18002f937  mov     rcx, [r12]
0x18002f93b  xorps   xmm0, xmm0
0x18002f93e  xor     eax, eax
0x18002f940  add     rcx, 10h; lpCriticalSection
0x18002f944  mov     dword ptr [rbp+190h+Buffer], eax
0x18002f94a  movups  [rbp+190h+var_5C], xmm0
0x18002f951  mov     [rbp+190h+var_3C], eax
0x18002f957  movups  [rbp+190h+var_4C], xmm0
0x18002f95e  movups  [rbp+190h+var_200], xmm0
0x18002f962  call    cs:__imp_EnterCriticalSection
0x18002f968  mov     rax, [r12]
0x18002f96c  xor     edi, edi
0x18002f96e  mov     ecx, [rax+50h]
0x18002f971  lea     esi, [rdi+1]
0x18002f974  and     ecx, 80h
0x18002f97a  mov     r13d, esi
0x18002f97d  cmp     cs:dword_1800C8568, edi
0x18002f983  mov     [rsp+290h+var_260], ecx
0x18002f987  jbe     loc_18002FAF6
0x18002f98d  mov     r15, cs:qword_1800C8560
0x18002f994  mov     eax, edi
0x18002f996  imul    r14, rax, 0A8h
0x18002f99d  test    ecx, ecx
0x18002f99f  jz      loc_18002FA26
0x18002f9a5  cmp     [r14+r15+8], sil
0x18002f9aa  jnz     short loc_18002FA26
0x18002f9ac  test    cs:byte_1800C8404, 8
0x18002f9b3  jz      loc_18002FA75
0x18002f9b9  xor     eax, eax
0x18002f9bb  mov     [rbp+190h+Buffer], ax
0x18002f9c2  test    rbx, rbx
0x18002f9c5  jz      short loc_18002F9E4
0x18002f9c7  mov     ecx, [rbx+60h]; Value
0x18002f9ca  cmp     ecx, 0FFFFFFFFh
0x18002f9cd  jz      short loc_18002F9E4
0x18002f9cf  lea     r9d, [rax+0Ah]; Radix
0x18002f9d3  lea     r8d, [rax+14h]; BufferCount
0x18002f9d7  lea     rdx, [rbp+190h+Buffer]; Buffer
0x18002f9de  call    cs:__imp__itow_s
0x18002f9e4  test    cs:byte_1800C8404, 8
0x18002f9eb  jz      loc_18002FA75
0x18002f9f1  lea     rax, [rbp+190h+Buffer]
0x18002f9f8  mov     [rsp+290h+var_268], rax
0x18002f9fd  lea     r9, [rbp+190h+var_200]
0x18002fa01  lea     r8, aAcceptnewlinkS; "AcceptNewLink: Skipping version 1 Admin"...
0x18002fa08  mov     [rsp+290h+var_270], 0
0x18002fa11  lea     rdx, RasDdmParamTraceError
0x18002fa18  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002fa1f  call    McTemplateU0zjzz_EventWriteTransfer
0x18002fa24  jmp     short loc_18002FA75
0x18002fa26  cmp     qword ptr [r14+r15+48h], 0
0x18002fa2c  jz      short loc_18002FA75
0x18002fa2e  test    r13d, r13d
0x18002fa31  jz      short loc_18002FA5E
0x18002fa33  lea     rdx, [rbp+190h+var_1F0]; struct _RAS_PORT_0 *
0x18002fa37  mov     rcx, rbx; this
0x18002fa3a  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_0@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_0 *)
0x18002fa3f  test    eax, eax
0x18002fa41  jnz     short loc_18002FA88
0x18002fa43  lea     rdx, [rsp+290h+var_250]; struct _RAS_PORT_1 *
0x18002fa48  mov     rcx, rbx; this
0x18002fa4b  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_1@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_1 *)
0x18002fa50  test    eax, eax
0x18002fa52  jnz     short loc_18002FA88
0x18002fa54  xor     r13d, r13d
0x18002fa57  and     dword ptr [rbx+84h], 0FFFFFFDFh
0x18002fa5e  mov     rax, [r14+r15+48h]
0x18002fa63  lea     rdx, [rsp+290h+var_250]
0x18002fa68  lea     rcx, [rbp+190h+var_1F0]
0x18002fa6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa71  test    eax, eax
0x18002fa73  jz      short loc_18002FAAC
0x18002fa75  add     edi, esi
0x18002fa77  cmp     edi, cs:dword_1800C8568
0x18002fa7d  jnb     short loc_18002FAF6
0x18002fa7f  mov     ecx, [rsp+290h+var_260]
0x18002fa83  jmp     loc_18002F98D
0x18002fa88  mov     rax, [rbx]
0x18002fa8b  mov     rcx, rbx
0x18002fa8e  mov     rax, [rax+0B0h]
0x18002fa95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa9a  mov     rcx, [r12]
0x18002fa9e  add     rcx, 10h; lpCriticalSection
0x18002faa2  call    cs:__imp_LeaveCriticalSection
0x18002faa8  xor     eax, eax
0x18002faaa  jmp     short loc_18002FB0D
0x18002faac  mov     rax, [rbx]
0x18002faaf  mov     rcx, rbx
0x18002fab2  mov     rax, [rax+0B0h]
0x18002fab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fabe  xor     ebx, ebx
0x18002fac0  test    edi, edi
0x18002fac2  jz      short loc_18002FAF2
0x18002fac4  mov     eax, ebx
0x18002fac6  imul    rcx, rax, 0A8h
0x18002facd  mov     rax, cs:qword_1800C8560
0x18002fad4  mov     rax, [rcx+rax+68h]
0x18002fad9  test    rax, rax
0x18002fadc  jz      short loc_18002FAEC
0x18002fade  lea     rdx, [rsp+290h+var_250]
0x18002fae3  lea     rcx, [rbp+190h+var_1F0]
0x18002fae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faec  add     ebx, esi
0x18002faee  cmp     ebx, edi
0x18002faf0  jb      short loc_18002FAC4
0x18002faf2  xor     esi, esi
0x18002faf4  jmp     short loc_18002FAFD
0x18002faf6  or      dword ptr [rbx+84h], 20h
0x18002fafd  mov     rcx, [r12]
0x18002fb01  add     rcx, 10h; lpCriticalSection
0x18002fb05  call    cs:__imp_LeaveCriticalSection
0x18002fb0b  mov     eax, esi
0x18002fb0d  mov     rcx, [rbp+190h+var_38]
0x18002fb14  xor     rcx, rsp; StackCookie
0x18002fb17  call    __security_check_cookie
0x18002fb1c  mov     rbx, [rsp+290h+arg_10]
0x18002fb24  add     rsp, 260h
0x18002fb2b  pop     r15
0x18002fb2d  pop     r14
0x18002fb2f  pop     r13
0x18002fb31  pop     r12
0x18002fb33  pop     rdi
0x18002fb34  pop     rsi
0x18002fb35  pop     rbp
0x18002fb36  retn
```
