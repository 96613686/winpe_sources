# CDimInterfaceTable::ServiceControlDeviceEvent(ulong,void *)

- ea: `0x180005134`
- end: `0x18000532e`
- name: `?ServiceControlDeviceEvent@CDimInterfaceTable@@QEAAXKPEAX@Z`
- size: `506`
- prototype: `void __fastcall(CDimInterfaceTable *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011c70`

## callees

- `0x180001610`
- `0x180003f40`
- `0x180005134`
- `0x180005340`
- `0x180005358`
- `0x180005670`
- `0x180007bf0`
- `0x18000def0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800051b0`
- `msvcrt!wcsrchr` at `0x1800051c2`
- `msvcrt!wcsrchr` at `0x1800051b0`
- `msvcrt!wcsrchr` at `0x1800051c2`

## string_xrefs

- `0x1800052a3`: `Device removed:[%ws]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDimInterfaceTable::ServiceControlDeviceEvent(CDimInterfaceTable *this, int a2, void *a3)
{
  CDimInterfaceTable *v5; // rdi
  unsigned __int16 *v6; // rsi
  wchar_t *v7; // rax
  wchar_t *v8; // rbx
  wchar_t v9; // r15
  void *v10; // rax
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  std::tr1::_Ref_count_base *v12; // [rsp+38h] [rbp-C8h]
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( !a3 )
    return;
  if ( *((_DWORD *)a3 + 1) != 5 )
    return;
  if ( ((a2 - 0x8000) & 0xFFFFFFFB) != 0 )
    return;
  v5 = g_pCDimInterfaceTable;
  v6 = wcsrchr((const wchar_t *)a3 + 14, 0x7Bu);
  v7 = wcsrchr((const wchar_t *)a3 + 14, 0x7Du);
  v8 = v7;
  if ( !v6 || !v7 )
    return;
  v9 = v7[1];
  v7[1] = 0;
  CDimInterfaceTable::AcquireExclusive(v5);
  CDimInterfaceTable::GetInterfaceByName((__int64)v5, &v11, (__int64)v6, 0);
  if ( a2 == 0x8000 )
  {
    if ( !v11 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"Device arrival:[%ws]", v6);
        if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminInfo, &v13);
      }
      CDimInterfaceTable::ReleaseExclusive(v5);
      CDimInterfaceTable::RegLoadInterfaces(v5, v6, 0, 0, 0);
      goto LABEL_19;
    }
  }
  else if ( v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"Device removed:[%ws]", v6);
      if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminInfo, &v13);
    }
    v10 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    CDimInterfaceTable::RemoveInterface(v5, v10);
  }
  CDimInterfaceTable::ReleaseExclusive(v5);
LABEL_19:
  if ( v12 )
    std::tr1::_Ref_count_base::_Decref(v12);
  v8[1] = v9;
}

```

## disassembly

```asm
0x180005134  push    rbp
0x180005136  push    rbx
0x180005137  push    rsi
0x180005138  push    rdi
0x180005139  push    r14
0x18000513b  push    r15
0x18000513d  lea     rbp, [rsp-758h]
0x180005145  sub     rsp, 858h
0x18000514c  mov     rax, cs:__security_cookie
0x180005153  xor     rax, rsp
0x180005156  mov     [rbp+780h+var_40], rax
0x18000515d  mov     rbx, r8
0x180005160  mov     r14d, edx
0x180005163  xor     eax, eax
0x180005165  mov     [rsp+880h+var_840], eax
0x180005169  xor     edx, edx; Val
0x18000516b  mov     r8d, 7FCh; Size
0x180005171  lea     rcx, [rsp+880h+var_83C]; void *
0x180005176  call    memset_0
0x18000517b  test    rbx, rbx
0x18000517e  jz      loc_18000530F
0x180005184  cmp     dword ptr [rbx+4], 5
0x180005188  jnz     loc_18000530F
0x18000518e  lea     eax, [r14-8000h]
0x180005195  test    eax, 0FFFFFFFBh
0x18000519a  jnz     loc_18000530F
0x1800051a0  mov     rdi, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x1800051a7  mov     edx, 7Bh ; '{'; Ch
0x1800051ac  lea     rcx, [rbx+1Ch]; Str
0x1800051b0  call    cs:__imp_wcsrchr
0x1800051b6  mov     rsi, rax
0x1800051b9  mov     edx, 7Dh ; '}'; Ch
0x1800051be  lea     rcx, [rbx+1Ch]; Str
0x1800051c2  call    cs:__imp_wcsrchr
0x1800051c8  mov     rbx, rax
0x1800051cb  test    rsi, rsi
0x1800051ce  jz      loc_18000530F
0x1800051d4  test    rax, rax
0x1800051d7  jz      loc_18000530F
0x1800051dd  movzx   r15d, word ptr [rax+2]
0x1800051e2  xor     ecx, ecx
0x1800051e4  mov     [rax+2], cx
0x1800051e8  mov     rcx, rdi; this
0x1800051eb  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x1800051f0  xor     r9d, r9d
0x1800051f3  mov     r8, rsi
0x1800051f6  lea     rdx, [rsp+880h+var_850]
0x1800051fb  mov     rcx, rdi
0x1800051fe  call    ?GetInterfaceByName@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAG_N@Z; CDimInterfaceTable::GetInterfaceByName(ushort *,bool)
0x180005203  cmp     r14d, 8000h
0x18000520a  jnz     short loc_180005288
0x18000520c  cmp     [rsp+880h+var_850], 0
0x180005212  jnz     short loc_18000527D
0x180005214  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x18000521b  jz      short loc_180005259
0x18000521d  xor     eax, eax
0x18000521f  mov     word ptr [rsp+880h+var_840], ax
0x180005224  mov     r8, rsi
0x180005227  lea     rdx, aDeviceArrivalW; "Device arrival:[%ws]"
0x18000522e  lea     rcx, [rsp+880h+var_840]
0x180005233  call    FormatRRASErrorString
0x180005238  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x18000523f  jz      short loc_180005259
0x180005241  lea     r8, [rsp+880h+var_840]
0x180005246  lea     rdx, RasDimTraceAdminInfo
0x18000524d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005254  call    McTemplateU0z_EventWriteTransfer
0x180005259  mov     rcx, rdi; this
0x18000525c  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x180005261  mov     [rsp+880h+var_860], 0; struct _DIM_COMPARTMENT_INTERFACE *
0x18000526a  xor     r9d, r9d; unsigned int
0x18000526d  xor     r8d, r8d; struct _GUID *
0x180005270  mov     rdx, rsi; unsigned __int16 *
0x180005273  mov     rcx, rdi; this
0x180005276  call    ?RegLoadInterfaces@CDimInterfaceTable@@QEAAKPEAGPEAU_GUID@@KPEAU_DIM_COMPARTMENT_INTERFACE@@@Z; CDimInterfaceTable::RegLoadInterfaces(ushort *,_GUID *,ulong,_DIM_COMPARTMENT_INTERFACE *)
0x18000527b  jmp     short loc_180005286
0x18000527d  mov     rcx, rdi; this
0x180005280  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x180005285  nop
0x180005286  jmp     short loc_1800052FA
0x180005288  cmp     [rsp+880h+var_850], 0
0x18000528e  jz      short loc_1800052F1
0x180005290  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180005297  jz      short loc_1800052D5
0x180005299  xor     eax, eax
0x18000529b  mov     word ptr [rsp+880h+var_840], ax
0x1800052a0  mov     r8, rsi
0x1800052a3  lea     rdx, aDeviceRemovedW; "Device removed:[%ws]"
0x1800052aa  lea     rcx, [rsp+880h+var_840]
0x1800052af  call    FormatRRASErrorString
0x1800052b4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x1800052bb  jz      short loc_1800052D5
0x1800052bd  lea     r8, [rsp+880h+var_840]
0x1800052c2  lea     rdx, RasDimTraceAdminInfo
0x1800052c9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800052d0  call    McTemplateU0z_EventWriteTransfer
0x1800052d5  mov     rcx, [rsp+880h+var_850]
0x1800052da  mov     rax, [rcx]
0x1800052dd  mov     rax, [rax+10h]
0x1800052e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e6  mov     rdx, rax; void *
0x1800052e9  mov     rcx, rdi; this
0x1800052ec  call    ?RemoveInterface@CDimInterfaceTable@@EEAAXQEAX@Z; CDimInterfaceTable::RemoveInterface(void * const)
0x1800052f1  mov     rcx, rdi; this
0x1800052f4  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x1800052f9  nop
0x1800052fa  mov     rcx, [rsp+880h+var_848]; this
0x1800052ff  test    rcx, rcx
0x180005302  jz      short loc_18000530A
0x180005304  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180005309  nop
0x18000530a  mov     [rbx+2], r15w
0x18000530f  mov     rcx, [rbp+780h+var_40]
0x180005316  xor     rcx, rsp; StackCookie
0x180005319  call    __security_check_cookie
0x18000531e  add     rsp, 858h
0x180005325  pop     r15
0x180005327  pop     r14
0x180005329  pop     rdi
0x18000532a  pop     rsi
0x18000532b  pop     rbx
0x18000532c  pop     rbp
0x18000532d  retn
```
