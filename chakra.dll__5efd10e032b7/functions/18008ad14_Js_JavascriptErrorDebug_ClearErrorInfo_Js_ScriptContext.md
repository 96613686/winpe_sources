# Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)

- ea: `0x18008ad14`
- end: `0x18008addb`
- name: `?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z`
- size: `199`
- prototype: `void __fastcall(struct Js::ScriptContext *)`
- caller_count: `96`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004054`
- `0x1800060f4`
- `0x180088e54`
- `0x1800896cc`
- `0x1800898f4`
- `0x18008c3a0`
- `0x18008e884`
- `0x180091470`
- `0x180091978`
- `0x180091d10`
- `0x1802a3120`
- `0x1802a3be0`
- `0x18032c3a0`
- `0x18032fc90`
- `0x180333bb0`
- `0x180333d60`
- `0x180333fa0`
- `0x180334260`
- `0x180334480`
- `0x18035d990`
- `0x18035f010`
- `0x18035f130`
- `0x18035ff60`
- `0x180367cc0`
- `0x18036d3d0`
- `0x180384550`
- `0x180384eb8`
- `0x180385144`
- `0x180385660`
- `0x180391a70`
- `0x18039a854`
- `0x18039f8e0`
- `0x1803b89f0`
- `0x1803e2684`
- `0x180472810`
- `0x1804748b0`
- `0x180474d80`
- `0x180474f70`
- `0x180475140`
- `0x180475310`
- `0x1804754e0`
- `0x1804756a0`
- `0x180475890`
- `0x180475a70`
- `0x180475c90`
- `0x180475e70`
- `0x180476060`
- `0x180476250`
- `0x180476440`
- `0x180476630`

## callees

- `0x18008ad14`
- `0x18032e784`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18008ad77`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18008ad77`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18008adb5`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18008adb5`

## pseudocode

```c
void __fastcall Js::JavascriptErrorDebug::ClearErrorInfo(struct Js::ScriptContext *a1)
{
  _QWORD *v1; // rbx
  void (*Function)(void); // rax
  const WCHAR *v3; // rax
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-18h] BYREF

  v1 = (_QWORD *)(*((_QWORD *)a1 + 110) + 7992LL);
  if ( !*(_BYTE *)(*((_QWORD *)a1 + 110) + 8008LL) )
  {
    v3 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*v1 + 8LL))(*((_QWORD *)a1 + 110) + 7992LL);
    v1[1] = LoadLibraryExW(v3, 0, 0x800u);
    *((_BYTE *)v1 + 16) = 1;
  }
  if ( v1[1]
    && ((Function = (void (*)(void))v1[3]) != 0
     || (Function = (void (*)(void))DelayLoadLibrary::GetFunction((DelayLoadLibrary *)v1, "RoClearError"),
         (v1[3] = Function) != 0)) )
  {
    Function();
  }
  else
  {
    pperrinfo = 0;
    if ( !GetErrorInfo(0, &pperrinfo) )
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x18008ad14  mov     [rsp+arg_8], rbx
0x18008ad19  mov     [rsp+arg_0], rcx
0x18008ad1e  push    rdi
0x18008ad1f  sub     rsp, 30h
0x18008ad23  mov     rax, [rsp+38h+arg_0]
0x18008ad28  mov     rbx, [rax+370h]
0x18008ad2f  add     rbx, 1F38h
0x18008ad36  cmp     byte ptr [rbx+10h], 0
0x18008ad3a  jz      short loc_18008AD5D
0x18008ad3c  cmp     qword ptr [rbx+8], 0
0x18008ad41  jz      short loc_18008ADA5
0x18008ad43  mov     rax, [rbx+18h]
0x18008ad47  test    rax, rax
0x18008ad4a  jz      short loc_18008AD8D
0x18008ad4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad51  mov     rbx, [rsp+38h+arg_8]
0x18008ad56  add     rsp, 30h
0x18008ad5a  pop     rdi
0x18008ad5b  retn
0x18008ad5d  mov     rax, [rbx]
0x18008ad60  mov     rcx, rbx
0x18008ad63  mov     rax, [rax+8]
0x18008ad67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad6c  mov     rcx, rax; lpLibFileName
0x18008ad6f  xor     edx, edx; hFile
0x18008ad71  mov     r8d, 800h; dwFlags
0x18008ad77  call    cs:__imp_LoadLibraryExW
0x18008ad7e  nop     dword ptr [rax+rax+00h]
0x18008ad83  mov     [rbx+8], rax
0x18008ad87  mov     byte ptr [rbx+10h], 1
0x18008ad8b  jmp     short loc_18008AD3C
0x18008ad8d  lea     rdx, aRoclearerror; "RoClearError"
0x18008ad94  mov     rcx, rbx; this
0x18008ad97  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x18008ad9c  mov     [rbx+18h], rax
0x18008ada0  test    rax, rax
0x18008ada3  jnz     short loc_18008AD4C
0x18008ada5  lea     rdx, [rsp+38h+pperrinfo]; pperrinfo
0x18008adaa  mov     [rsp+38h+pperrinfo], 0
0x18008adb3  xor     ecx, ecx; dwReserved
0x18008adb5  call    cs:__imp_GetErrorInfo
0x18008adbc  nop     dword ptr [rax+rax+00h]
0x18008adc1  test    eax, eax
0x18008adc3  jnz     short loc_18008AD51
0x18008adc5  mov     rcx, [rsp+38h+pperrinfo]
0x18008adca  mov     rax, [rcx]
0x18008adcd  mov     rax, [rax+10h]
0x18008add1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008add6  jmp     loc_18008AD51
```
