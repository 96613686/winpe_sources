# ServiceHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180010c40`
- end: `0x180010f5a`
- name: `?ServiceHandlerEx@@YAKKKPEAX0@Z`
- size: `794`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000e848`
- `0x180010c40`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010ee7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010ee7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180010df9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180010df9`

## pseudocode

```c
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  _BYTE *v5; // rax
  char v6; // bl
  unsigned int v7; // esi

  v5 = WPP_GLOBAL_Control;
  v6 = 1;
  LOBYTE(dwEventType) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      dwEventType,
      (_BYTE)lpEventData,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v5 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  switch ( dwControl )
  {
    case 1u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)dwEventType && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_60;
LABEL_59:
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v5 + 2), dwEventType, (_DWORD)lpEventData, *((_QWORD *)v5 + 5));
LABEL_60:
      BthServSetState(3u);
      SetEvent(Globals);
      goto LABEL_61;
    case 2u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)dwEventType && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      goto LABEL_45;
    case 3u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)dwEventType && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
LABEL_45:
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v5 + 2), dwEventType, (_DWORD)lpEventData, *((_QWORD *)v5 + 5));
      goto LABEL_61;
    case 4u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v5 + 2), dwEventType, (_DWORD)lpEventData, *((_QWORD *)v5 + 5));
      }
      SetServiceStatus(hServiceStatus, &ServiceStatus);
      goto LABEL_61;
    case 5u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)dwEventType && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_60;
      goto LABEL_59;
    case 0xEu:
      if ( !hLibModule )
        goto LABEL_62;
      ((void (__fastcall *)(__int64, __int64, LPVOID, LPVOID))qword_180047108)(2, dwEventType, lpEventData, lpContext);
LABEL_61:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_62;
  }
  LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 3u;
  if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v5 + 2), dwEventType, (_DWORD)lpEventData, *((_QWORD *)v5 + 5));
    v5 = WPP_GLOBAL_Control;
  }
  v7 = 120;
LABEL_62:
  if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 5u )
    v6 = 0;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(dwEventType) = v6;
    LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v5 + 2), dwEventType, (_DWORD)lpEventData, *((_QWORD *)v5 + 5));
  }
  return v7;
}

```

## disassembly

```asm
0x180010c40  mov     [rsp+arg_0], rbx
0x180010c45  mov     [rsp+arg_8], rbp
0x180010c4a  mov     [rsp+arg_10], rsi
0x180010c4f  push    rdi
0x180010c50  push    r14
0x180010c52  push    r15
0x180010c54  sub     rsp, 50h
0x180010c58  mov     edi, ecx
0x180010c5a  mov     rax, cs:WPP_GLOBAL_Control
0x180010c61  lea     rbp, WPP_GLOBAL_Control
0x180010c68  mov     ebx, 1
0x180010c6d  cmp     rax, rbp
0x180010c70  jz      short loc_180010C7C
0x180010c72  cmp     byte ptr [rax+19h], 5
0x180010c76  jb      short loc_180010C7C
0x180010c78  mov     dl, bl
0x180010c7a  jmp     short loc_180010C7E
0x180010c7c  xor     dl, dl
0x180010c7e  lea     r14, WPP_RECORDER_INITIALIZED
0x180010c85  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010c8c  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180010c93  setnz   r8b
0x180010c97  test    dl, dl
0x180010c99  jnz     short loc_180010CA0
0x180010c9b  test    r8b, r8b
0x180010c9e  jz      short loc_180010CC0
0x180010ca0  mov     r9, [rax+28h]
0x180010ca4  mov     rcx, [rax+10h]
0x180010ca8  mov     [rsp+68h+var_30], r15
0x180010cad  mov     [rsp+68h+var_38], 0Ch
0x180010cb4  call    WPP_RECORDER_AND_TRACE_SF_s
0x180010cb9  mov     rax, cs:WPP_GLOBAL_Control
0x180010cc0  xor     esi, esi
0x180010cc2  mov     ecx, edi
0x180010cc4  sub     ecx, ebx
0x180010cc6  jz      loc_180010E94
0x180010ccc  sub     ecx, ebx
0x180010cce  jz      loc_180010E59
0x180010cd4  sub     ecx, ebx
0x180010cd6  jz      loc_180010E0A
0x180010cdc  sub     ecx, ebx
0x180010cde  jz      loc_180010DA5
0x180010ce4  sub     ecx, ebx
0x180010ce6  jz      short loc_180010D63
0x180010ce8  cmp     ecx, 9
0x180010ceb  jz      short loc_180010D40
0x180010ced  cmp     rax, rbp
0x180010cf0  jz      short loc_180010CFC
0x180010cf2  cmp     byte ptr [rax+19h], 3
0x180010cf6  jb      short loc_180010CFC
0x180010cf8  mov     dl, bl
0x180010cfa  jmp     short loc_180010CFE
0x180010cfc  xor     dl, dl
0x180010cfe  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010d05  setnz   r8b
0x180010d09  test    dl, dl
0x180010d0b  jnz     short loc_180010D12
0x180010d0d  test    r8b, r8b
0x180010d10  jz      short loc_180010D36
0x180010d12  mov     r9, [rax+28h]
0x180010d16  mov     rcx, [rax+10h]
0x180010d1a  mov     dword ptr [rsp+68h+var_20], edi
0x180010d1e  mov     [rsp+68h+var_30], r15
0x180010d23  mov     [rsp+68h+var_38], 12h
0x180010d2a  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180010d2f  mov     rax, cs:WPP_GLOBAL_Control
0x180010d36  mov     esi, 78h ; 'x'
0x180010d3b  jmp     loc_180010EFA
0x180010d40  cmp     cs:hLibModule, rsi
0x180010d47  jz      loc_180010EFA
0x180010d4d  mov     rax, cs:qword_180047108
0x180010d54  mov     ecx, 2
0x180010d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d5e  jmp     loc_180010EF3
0x180010d63  cmp     rax, rbp
0x180010d66  jz      short loc_180010D72
0x180010d68  cmp     byte ptr [rax+19h], 4
0x180010d6c  jb      short loc_180010D72
0x180010d6e  mov     dl, bl
0x180010d70  jmp     short loc_180010D74
0x180010d72  xor     dl, dl
0x180010d74  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010d7b  setnz   r8b
0x180010d7f  test    dl, dl
0x180010d81  jnz     short loc_180010D8C
0x180010d83  test    r8b, r8b
0x180010d86  jz      loc_180010ED6
0x180010d8c  mov     dword ptr [rsp+68h+var_20], 5
0x180010d94  mov     [rsp+68h+var_30], r15
0x180010d99  mov     [rsp+68h+var_38], 11h
0x180010da0  jmp     loc_180010EC9
0x180010da5  cmp     rax, rbp
0x180010da8  jz      short loc_180010DB4
0x180010daa  cmp     byte ptr [rax+19h], 4
0x180010dae  jb      short loc_180010DB4
0x180010db0  mov     dl, bl
0x180010db2  jmp     short loc_180010DB6
0x180010db4  xor     dl, dl
0x180010db6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010dbd  setnz   r8b
0x180010dc1  test    dl, dl
0x180010dc3  jnz     short loc_180010DCA
0x180010dc5  test    r8b, r8b
0x180010dc8  jz      short loc_180010DEB
0x180010dca  mov     r9, [rax+28h]
0x180010dce  mov     rcx, [rax+10h]
0x180010dd2  mov     dword ptr [rsp+68h+var_20], 4
0x180010dda  mov     [rsp+68h+var_30], r15
0x180010ddf  mov     [rsp+68h+var_38], 0Dh
0x180010de6  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180010deb  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180010df2  lea     rdx, ServiceStatus; lpServiceStatus
0x180010df9  call    cs:__imp_SetServiceStatus
0x180010e00  nop     dword ptr [rax+rax+00h]
0x180010e05  jmp     loc_180010EF3
0x180010e0a  cmp     rax, rbp
0x180010e0d  jz      short loc_180010E19
0x180010e0f  cmp     byte ptr [rax+19h], 4
0x180010e13  jb      short loc_180010E19
0x180010e15  mov     dl, bl
0x180010e17  jmp     short loc_180010E1B
0x180010e19  xor     dl, dl
0x180010e1b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010e22  setnz   r8b
0x180010e26  test    dl, dl
0x180010e28  jnz     short loc_180010E33
0x180010e2a  test    r8b, r8b
0x180010e2d  jz      loc_180010EFA
0x180010e33  mov     dword ptr [rsp+68h+var_20], 3
0x180010e3b  mov     [rsp+68h+var_30], r15
0x180010e40  mov     [rsp+68h+var_38], 0Eh
0x180010e47  mov     r9, [rax+28h]
0x180010e4b  mov     rcx, [rax+10h]
0x180010e4f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180010e54  jmp     loc_180010EF3
0x180010e59  cmp     rax, rbp
0x180010e5c  jz      short loc_180010E68
0x180010e5e  cmp     byte ptr [rax+19h], 4
0x180010e62  jb      short loc_180010E68
0x180010e64  mov     dl, bl
0x180010e66  jmp     short loc_180010E6A
0x180010e68  xor     dl, dl
0x180010e6a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010e71  setnz   r8b
0x180010e75  test    dl, dl
0x180010e77  jnz     short loc_180010E7E
0x180010e79  test    r8b, r8b
0x180010e7c  jz      short loc_180010EFA
0x180010e7e  mov     dword ptr [rsp+68h+var_20], 2
0x180010e86  mov     [rsp+68h+var_30], r15
0x180010e8b  mov     [rsp+68h+var_38], 0Fh
0x180010e92  jmp     short loc_180010E47
0x180010e94  cmp     rax, rbp
0x180010e97  jz      short loc_180010EA3
0x180010e99  cmp     byte ptr [rax+19h], 4
0x180010e9d  jb      short loc_180010EA3
0x180010e9f  mov     dl, bl
0x180010ea1  jmp     short loc_180010EA5
0x180010ea3  xor     dl, dl
0x180010ea5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010eac  setnz   r8b
0x180010eb0  test    dl, dl
0x180010eb2  jnz     short loc_180010EB9
0x180010eb4  test    r8b, r8b
0x180010eb7  jz      short loc_180010ED6
0x180010eb9  mov     dword ptr [rsp+68h+var_20], ebx
0x180010ebd  mov     [rsp+68h+var_30], r15
0x180010ec2  mov     [rsp+68h+var_38], 10h
0x180010ec9  mov     r9, [rax+28h]
0x180010ecd  mov     rcx, [rax+10h]
0x180010ed1  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180010ed6  mov     ecx, 3; unsigned int
0x180010edb  call    ?BthServSetState@@YAHK@Z; BthServSetState(ulong)
0x180010ee0  mov     rcx, cs:?Globals@@3VBthServGlobals@@A; hEvent
0x180010ee7  call    cs:__imp_SetEvent
0x180010eee  nop     dword ptr [rax+rax+00h]
0x180010ef3  mov     rax, cs:WPP_GLOBAL_Control
0x180010efa  cmp     rax, rbp
0x180010efd  jz      short loc_180010F05
0x180010eff  cmp     byte ptr [rax+19h], 5
0x180010f03  jnb     short loc_180010F07
0x180010f05  xor     bl, bl
0x180010f07  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010f0e  setnz   r8b
0x180010f12  test    bl, bl
0x180010f14  jnz     short loc_180010F1B
0x180010f16  test    r8b, r8b
0x180010f19  jz      short loc_180010F3D
0x180010f1b  mov     r9, [rax+28h]
0x180010f1f  mov     dl, bl
0x180010f21  mov     ecx, esi
0x180010f23  mov     [rsp+68h+var_20], rcx
0x180010f28  mov     rcx, [rax+10h]
0x180010f2c  mov     [rsp+68h+var_30], r15
0x180010f31  mov     [rsp+68h+var_38], 13h
0x180010f38  call    WPP_RECORDER_AND_TRACE_SF_si
0x180010f3d  lea     r11, [rsp+68h+var_18]
0x180010f42  mov     eax, esi
0x180010f44  mov     rbx, [r11+20h]
0x180010f48  mov     rbp, [r11+28h]
0x180010f4c  mov     rsi, [r11+30h]
0x180010f50  mov     rsp, r11
0x180010f53  pop     r15
0x180010f55  pop     r14
0x180010f57  pop     rdi
0x180010f58  retn
```
