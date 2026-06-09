# CSNOCplCore::OnLaunchRelevantTaskWindow(ulong)

- ea: `0x18000dd74`
- end: `0x18000de8a`
- name: `?OnLaunchRelevantTaskWindow@CSNOCplCore@@AEAAXK@Z`
- size: `278`
- prototype: `void __fastcall(CSNOCplCore *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d2e4`

## callees

- `0x18000ae44`
- `0x18000dae4`
- `0x18000dd74`
- `0x180010e9c`
- `0x180014274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ddbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ddbc`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000ddf4`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000ddf4`
- `USER32!SetCursor` at `0x18000dd96`
- `USER32!SetCursor` at `0x18000dd96`
- `USER32!SetCursor` at `0x18000de83`
- `USER32!LoadCursorW` at `0x18000dd8d`
- `USER32!LoadCursorW` at `0x18000dd8d`

## pseudocode

```c
void __fastcall CSNOCplCore::OnLaunchRelevantTaskWindow(CSNOCplCore *this, unsigned int a2)
{
  HCURSOR CursorW; // rax
  __int64 v5; // rsi
  HCURSOR v6; // r14
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  unsigned int Error; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v5 = 32LL * a2;
  v6 = SetCursor(CursorW);
  if ( *(_DWORD *)((char *)&g_rgTaskProp + v5) == 1 )
  {
    v7 = CoTaskMemAlloc(0x20u);
    v8 = v7;
    if ( v7 )
    {
      *(_OWORD *)v7 = *(_OWORD *)((char *)&g_rgTaskProp + v5 + 12);
      *((_QWORD *)v7 + 2) = CSNOCplCore::GetParentWindow(this);
      v8[6] = a2;
      if ( !SHCreateThread(OnLaunchRelevantTaskThread, v8, 8u, 0) )
      {
        Error = ResultFromKnownLastError();
        CoTaskMemFree(v8);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v11 = 111;
          v12 = Error;
LABEL_10:
          WPP_SF_d(v10[2], v11, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v12);
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 112;
        v12 = 2147942414LL;
        goto LABEL_10;
      }
    }
  }
  else if ( a2 == 1 )
  {
    CSNOCplCore::OnLaunchDiagnoseTask(this);
  }
  SetCursor(v6);
}

```

## disassembly

```asm
0x18000dd74  push    rbx
0x18000dd76  push    rbp
0x18000dd77  push    rsi
0x18000dd78  push    rdi
0x18000dd79  push    r14
0x18000dd7b  push    r15
0x18000dd7d  sub     rsp, 28h
0x18000dd81  mov     edi, edx
0x18000dd83  mov     rbp, rcx
0x18000dd86  mov     edx, 7F02h; lpCursorName
0x18000dd8b  xor     ecx, ecx; hInstance
0x18000dd8d  call    cs:__imp_LoadCursorW
0x18000dd93  mov     rcx, rax; hCursor
0x18000dd96  call    cs:__imp_SetCursor
0x18000dd9c  mov     esi, edi
0x18000dd9e  lea     r15, ?g_rgTaskProp@@3PAUtagTASKPROP@@A; tagTASKPROP near * g_rgTaskProp
0x18000dda5  shl     rsi, 5
0x18000dda9  mov     r14, rax
0x18000ddac  cmp     dword ptr [rsi+r15], 1
0x18000ddb1  jnz     loc_18000DE67
0x18000ddb7  mov     ecx, 20h ; ' '; cb
0x18000ddbc  call    cs:__imp_CoTaskMemAlloc
0x18000ddc2  mov     rbx, rax
0x18000ddc5  test    rax, rax
0x18000ddc8  jz      short loc_18000DE31
0x18000ddca  movups  xmm0, xmmword ptr [rsi+r15+0Ch]
0x18000ddd0  mov     rcx, rbp; this
0x18000ddd3  movdqu  xmmword ptr [rax], xmm0
0x18000ddd7  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x18000dddc  xor     r9d, r9d; pfnCallback
0x18000dddf  mov     [rbx+10h], rax
0x18000dde3  mov     rdx, rbx; pData
0x18000dde6  mov     [rbx+18h], edi
0x18000dde9  lea     rcx, ?OnLaunchRelevantTaskThread@@YAKPEAX@Z; pfnThreadProc
0x18000ddf0  lea     r8d, [r9+8]; flags
0x18000ddf4  call    cs:__imp_SHCreateThread
0x18000ddfa  test    eax, eax
0x18000ddfc  jnz     short loc_18000DE74
0x18000ddfe  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000de03  mov     rcx, rbx; pv
0x18000de06  mov     edi, eax
0x18000de08  call    cs:__imp_CoTaskMemFree
0x18000de0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de15  lea     rdx, WPP_GLOBAL_Control
0x18000de1c  cmp     rcx, rdx
0x18000de1f  jz      short loc_18000DE74
0x18000de21  test    byte ptr [rcx+1Ch], 2
0x18000de25  jz      short loc_18000DE74
0x18000de27  mov     edx, 6Fh ; 'o'
0x18000de2c  mov     r9d, edi
0x18000de2f  jmp     short loc_18000DE55
0x18000de31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de38  lea     rdx, WPP_GLOBAL_Control
0x18000de3f  cmp     rcx, rdx
0x18000de42  jz      short loc_18000DE74
0x18000de44  test    byte ptr [rcx+1Ch], 2
0x18000de48  jz      short loc_18000DE74
0x18000de4a  mov     edx, 70h ; 'p'
0x18000de4f  mov     r9d, 8007000Eh
0x18000de55  mov     rcx, [rcx+10h]
0x18000de59  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000de60  call    WPP_SF_d
0x18000de65  jmp     short loc_18000DE74
0x18000de67  cmp     edi, 1
0x18000de6a  jnz     short loc_18000DE74
0x18000de6c  mov     rcx, rbp; this
0x18000de6f  call    ?OnLaunchDiagnoseTask@CSNOCplCore@@AEAAJXZ; CSNOCplCore::OnLaunchDiagnoseTask(void)
0x18000de74  mov     rcx, r14
0x18000de77  add     rsp, 28h
0x18000de7b  pop     r15
0x18000de7d  pop     r14
0x18000de7f  pop     rdi
0x18000de80  pop     rsi
0x18000de81  pop     rbp
0x18000de82  pop     rbx
0x18000de83  jmp     cs:__imp_SetCursor
```
