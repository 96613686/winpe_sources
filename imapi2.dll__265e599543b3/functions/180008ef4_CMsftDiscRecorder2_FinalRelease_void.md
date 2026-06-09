# CMsftDiscRecorder2::FinalRelease(void)

- ea: `0x180008ef4`
- end: `0x180009084`
- name: `?FinalRelease@CMsftDiscRecorder2@@QEAAXXZ`
- size: `400`
- prototype: `void __fastcall(CMsftDiscRecorder2 *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180008e98`
- `0x180028c8c`

## callees

- `0x180008ef4`
- `0x18000908c`
- `0x180028ad8`
- `0x18002d510`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008ff3`
- `ole32!CoTaskMemFree` at `0x18000900b`
- `ole32!CoTaskMemFree` at `0x180009023`
- `ole32!CoTaskMemFree` at `0x180008ff3`
- `ole32!CoTaskMemFree` at `0x18000900b`
- `ole32!CoTaskMemFree` at `0x180009023`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fba`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fde`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fba`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fde`
- `KERNEL32!VirtualFree` at `0x18000905e`
- `KERNEL32!VirtualFree` at `0x18000905e`

## pseudocode

```c
void __fastcall CMsftDiscRecorder2::FinalRelease(CMsftDiscRecorder2 *this, __int64 a2, int a3)
{
  PVOID *v4; // rcx
  int v5; // edx
  void **v6; // rdx
  void *v7; // rcx
  void *v8; // rcx
  void **v9; // rdx
  void *v10; // rcx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, this);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_DWORD *)this + 59);
  if ( v5 && v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 188) & 4) != 0 && *((_BYTE *)v4 + 185) >= 3u )
    WPP_SF_qdDS((unsigned int)v4[22], v5, a3, (_DWORD)this, v5, v5, *((_QWORD *)this + 10));
  SysFreeString(*((BSTR *)this + 10));
  *((_QWORD *)this + 10) = 0;
  Imapi2Utility::CloseHandleAndNull((CMsftDiscRecorder2 *)((char *)this + 88), v6);
  SysFreeString(*((BSTR *)this + 12));
  *((_QWORD *)this + 12) = 0;
  SysFreeString(*((BSTR *)this + 13));
  *((_QWORD *)this + 13) = 0;
  SysFreeString(*((BSTR *)this + 14));
  *((_QWORD *)this + 14) = 0;
  SysFreeString(*((BSTR *)this + 15));
  *((_QWORD *)this + 15) = 0;
  CoTaskMemFree(*((LPVOID *)this + 18));
  v7 = (void *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 18) = 0;
  CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 16);
  *((_QWORD *)this + 19) = 0;
  CoTaskMemFree(v8);
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  Imapi2Utility::CloseHandleAndNull((CMsftDiscRecorder2 *)((char *)this + 160), v9);
  v10 = (void *)*((_QWORD *)this + 28);
  if ( v10 )
  {
    VirtualFree(v10, 0, 0x8000u);
    *((_QWORD *)this + 28) = 0;
  }
  *((_DWORD *)this + 58) = 0;
}

```

## disassembly

```asm
0x180008ef4  mov     [rsp+arg_0], rbx
0x180008ef9  push    rsi
0x180008efa  sub     rsp, 40h
0x180008efe  mov     rbx, rcx
0x180008f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f08  lea     rsi, WPP_GLOBAL_Control
0x180008f0f  cmp     rcx, rsi
0x180008f12  jz      short loc_180008F48
0x180008f14  test    byte ptr [rcx+0BCh], 2
0x180008f1b  jz      short loc_180008F48
0x180008f1d  cmp     byte ptr [rcx+0B9h], 4
0x180008f24  jb      short loc_180008F48
0x180008f26  mov     rcx, [rcx+0B0h]
0x180008f2d  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180008f34  mov     edx, 0Ah
0x180008f39  mov     r9, rbx
0x180008f3c  call    WPP_SF_q
0x180008f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f48  mov     edx, [rbx+0ECh]
0x180008f4e  test    edx, edx
0x180008f50  jz      short loc_180008F89
0x180008f52  cmp     rcx, rsi
0x180008f55  jz      short loc_180008F89
0x180008f57  test    byte ptr [rcx+0BCh], 4
0x180008f5e  jz      short loc_180008F89
0x180008f60  cmp     byte ptr [rcx+0B9h], 3
0x180008f67  jb      short loc_180008F89
0x180008f69  mov     rax, [rbx+50h]
0x180008f6d  mov     r9, rbx
0x180008f70  mov     rcx, [rcx+0B0h]
0x180008f77  mov     [rsp+48h+var_18], rax
0x180008f7c  mov     [rsp+48h+var_20], edx
0x180008f80  mov     [rsp+48h+var_28], edx
0x180008f84  call    WPP_SF_qdDS
0x180008f89  mov     rcx, [rbx+50h]; bstrString
0x180008f8d  call    cs:__imp_SysFreeString
0x180008f93  lea     rcx, [rbx+58h]; this
0x180008f97  mov     qword ptr [rbx+50h], 0
0x180008f9f  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180008fa4  mov     rcx, [rbx+60h]; bstrString
0x180008fa8  call    cs:__imp_SysFreeString
0x180008fae  mov     qword ptr [rbx+60h], 0
0x180008fb6  mov     rcx, [rbx+68h]; bstrString
0x180008fba  call    cs:__imp_SysFreeString
0x180008fc0  mov     qword ptr [rbx+68h], 0
0x180008fc8  mov     rcx, [rbx+70h]; bstrString
0x180008fcc  call    cs:__imp_SysFreeString
0x180008fd2  mov     qword ptr [rbx+70h], 0
0x180008fda  mov     rcx, [rbx+78h]; bstrString
0x180008fde  call    cs:__imp_SysFreeString
0x180008fe4  mov     qword ptr [rbx+78h], 0
0x180008fec  mov     rcx, [rbx+90h]; pv
0x180008ff3  call    cs:__imp_CoTaskMemFree
0x180008ff9  mov     rcx, [rbx+98h]; pv
0x180009000  mov     qword ptr [rbx+90h], 0
0x18000900b  call    cs:__imp_CoTaskMemFree
0x180009011  mov     rcx, [rbx+80h]; pv
0x180009018  mov     qword ptr [rbx+98h], 0
0x180009023  call    cs:__imp_CoTaskMemFree
0x180009029  lea     rcx, [rbx+0A0h]; this
0x180009030  mov     qword ptr [rbx+80h], 0
0x18000903b  mov     dword ptr [rbx+88h], 0
0x180009045  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x18000904a  mov     rcx, [rbx+0E0h]; lpAddress
0x180009051  test    rcx, rcx
0x180009054  jz      short loc_18000906F
0x180009056  xor     edx, edx; dwSize
0x180009058  mov     r8d, 8000h; dwFreeType
0x18000905e  call    cs:__imp_VirtualFree
0x180009064  mov     qword ptr [rbx+0E0h], 0
0x18000906f  mov     dword ptr [rbx+0E8h], 0
0x180009079  mov     rbx, [rsp+48h+arg_0]
0x18000907e  add     rsp, 40h
0x180009082  pop     rsi
0x180009083  retn
```
