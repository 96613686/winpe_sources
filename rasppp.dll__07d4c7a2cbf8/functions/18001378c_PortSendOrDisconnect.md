# PortSendOrDisconnect

- ea: `0x18001378c`
- end: `0x180013901`
- name: `PortSendOrDisconnect`
- size: `373`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800023a8`
- `0x180004388`
- `0x18000d1b4`
- `0x18000d284`
- `0x18000d480`
- `0x18000d8e4`
- `0x18000da74`
- `0x18000db70`
- `0x18000dda4`
- `0x18000de5c`
- `0x18000df18`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180012dcc`
- `0x18001378c`
- `0x18002a138`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall PortSendOrDisconnect(__int64 a1, unsigned int a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rdx
  int v6; // r15d
  unsigned int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r8
  int v10; // eax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v13 = 0;
  v12 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v4 = (__int64 *)(a1 + 16);
  if ( qword_18004CAB8 && (qword_18004CAB8(*v4, *(_QWORD *)(a1 + 40), a2, &v13, &v12), (v5 = v13) != 0) )
  {
    a2 = v12;
    v6 = 1;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 40);
    v6 = 0;
    v13 = v5;
    v12 = a2;
  }
  v7 = (*((__int64 (__fastcall **)(__int64, __int64, _QWORD))&xmmword_18004C460 + 1))(*v4, v5, a2);
  v8 = v7;
  if ( v7 )
  {
    if ( byte_18004CF33 < 0 )
    {
      v9 = *v4;
      LOWORD(v14) = 0;
      FormatRRASErrorString((wchar_t *)&v14, L"RasPortSend on port %d failed: %d", v9, v7);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceError,
          (const wchar_t *)&v14);
    }
    *(_DWORD *)(a1 + 56) |= 0x8000u;
    v10 = *(_DWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 1496) = v8;
    NotifyCaller(a1, (v10 & 4) != 0 ? 23 : 10, (unsigned int *)(a1 + 1496));
  }
  if ( v6 )
    ((void (__fastcall *)(__int64))qword_18004CAC0)(v13);
  return v8;
}

```

## disassembly

```asm
0x18001378c  mov     [rsp-8+arg_10], rbx
0x180013791  push    rbp
0x180013792  push    rsi
0x180013793  push    rdi
0x180013794  push    r14
0x180013796  push    r15
0x180013798  lea     rbp, [rsp-750h]
0x1800137a0  sub     rsp, 850h
0x1800137a7  mov     rax, cs:__security_cookie
0x1800137ae  xor     rax, rsp
0x1800137b1  mov     [rbp+770h+var_30], rax
0x1800137b8  mov     r14d, edx
0x1800137bb  mov     [rsp+870h+var_838], 0
0x1800137c4  mov     rsi, rcx
0x1800137c7  mov     [rsp+870h+var_840], 0
0x1800137cf  xor     eax, eax
0x1800137d1  lea     rcx, [rsp+870h+var_82C]; void *
0x1800137d6  xor     edx, edx; Val
0x1800137d8  mov     [rsp+870h+var_830], eax
0x1800137dc  mov     r8d, 7FCh; Size
0x1800137e2  call    memset_0
0x1800137e7  mov     rax, cs:qword_18004CAB8
0x1800137ee  lea     rbx, [rsi+10h]
0x1800137f2  test    rax, rax
0x1800137f5  jz      short loc_18001382C
0x1800137f7  mov     rdx, [rsi+28h]
0x1800137fb  lea     rcx, [rsp+870h+var_840]
0x180013800  mov     [rsp+870h+var_850], rcx
0x180013805  lea     r9, [rsp+870h+var_838]
0x18001380a  mov     rcx, [rbx]
0x18001380d  mov     r8d, r14d
0x180013810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013815  mov     rdx, [rsp+870h+var_838]
0x18001381a  test    rdx, rdx
0x18001381d  jz      short loc_18001382C
0x18001381f  mov     r14d, [rsp+870h+var_840]
0x180013824  mov     r15d, 1
0x18001382a  jmp     short loc_18001383D
0x18001382c  mov     rdx, [rsi+28h]
0x180013830  xor     r15d, r15d
0x180013833  mov     [rsp+870h+var_838], rdx
0x180013838  mov     [rsp+870h+var_840], r14d
0x18001383d  mov     rcx, [rbx]
0x180013840  mov     r8d, r14d
0x180013843  mov     rax, qword ptr cs:xmmword_18004C460+8
0x18001384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001384f  mov     edi, eax
0x180013851  test    eax, eax
0x180013853  jz      short loc_1800138C3
0x180013855  cmp     cs:byte_18004CF33, 0
0x18001385c  jge     short loc_18001389D
0x18001385e  mov     r8, [rbx]
0x180013861  lea     rdx, aRasportsendOnP; "RasPortSend on port %d failed: %d"
0x180013868  xor     ecx, ecx
0x18001386a  mov     r9d, eax
0x18001386d  mov     word ptr [rsp+870h+var_830], cx
0x180013872  lea     rcx, [rsp+870h+var_830]
0x180013877  call    FormatRRASErrorString
0x18001387c  cmp     cs:byte_18004CF33, 0
0x180013883  jge     short loc_18001389D
0x180013885  lea     r8, [rsp+870h+var_830]
0x18001388a  lea     rdx, RasPppTraceError
0x180013891  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013898  call    McTemplateU0z_EventWriteTransfer
0x18001389d  bts     dword ptr [rsi+38h], 0Fh
0x1800138a2  lea     r8, [rsi+5D8h]
0x1800138a9  mov     eax, [rsi+38h]
0x1800138ac  mov     rcx, rsi
0x1800138af  and     al, 4
0x1800138b1  mov     [r8], edi
0x1800138b4  neg     al
0x1800138b6  sbb     edx, edx
0x1800138b8  and     edx, 0Dh
0x1800138bb  add     edx, 0Ah
0x1800138be  call    NotifyCaller
0x1800138c3  test    r15d, r15d
0x1800138c6  jz      short loc_1800138D9
0x1800138c8  mov     rcx, [rsp+870h+var_838]
0x1800138cd  mov     rax, cs:qword_18004CAC0
0x1800138d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d9  mov     eax, edi
0x1800138db  mov     rcx, [rbp+770h+var_30]
0x1800138e2  xor     rcx, rsp; StackCookie
0x1800138e5  call    __security_check_cookie
0x1800138ea  mov     rbx, [rsp+870h+arg_10]
0x1800138f2  add     rsp, 850h
0x1800138f9  pop     r15
0x1800138fb  pop     r14
0x1800138fd  pop     rdi
0x1800138fe  pop     rsi
0x1800138ff  pop     rbp
0x180013900  retn
```
