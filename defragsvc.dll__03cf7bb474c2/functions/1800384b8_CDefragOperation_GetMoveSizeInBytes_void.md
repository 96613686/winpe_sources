# CDefragOperation::GetMoveSizeInBytes(void)

- ea: `0x1800384b8`
- end: `0x1800385a3`
- name: `?GetMoveSizeInBytes@CDefragOperation@@SA_KXZ`
- size: `235`
- prototype: `unsigned __int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053410`
- `0x1800568c0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800193a0`
- `0x18002a720`
- `0x1800384b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003857b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003857b`

## string_xrefs

- `0x1800384c7`: `CDefragOperation::GetMoveSizeInBytes`
- `0x180038538`: `MoveSizeKB`

## pseudocode

```c
__int64 CDefragOperation::GetMoveSizeInBytes(void)
{
  __int64 v0; // rbx
  HKEY v1; // rdx
  __int64 v2; // r9
  __int64 v3; // rbx
  unsigned __int16 *v5; // [rsp+20h] [rbp-78h]
  unsigned int v6; // [rsp+28h] [rbp-70h]
  struct _SECURITY_ATTRIBUTES *v7; // [rsp+38h] [rbp-60h]
  _BYTE v8[72]; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v9; // [rsp+A0h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v8, "CDefragOperation::GetMoveSizeInBytes", 578, 1);
  v0 = 128;
  hKey = 0;
  v9 = 128;
  if ( (int)SxRegCreateKeyExStateSeparated(L"Dfrg", v1, L"SOFTWARE\\Microsoft\\Dfrg", v2, v5, v6, 0x20019u, v7, &hKey) < 0 )
    goto LABEL_6;
  SxRegReadDWORD(hKey, L"MoveSizeKB", &v9, 1);
  v0 = v9;
  if ( v9 > 0x10000 )
  {
    v3 = 0x4000000;
    goto LABEL_7;
  }
  if ( v9 )
LABEL_6:
    v3 = v0 << 10;
  else
    v3 = 0x20000;
LABEL_7:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v8);
  return v3;
}

```

## disassembly

```asm
0x1800384b8  push    rbx
0x1800384ba  sub     rsp, 90h
0x1800384c1  mov     r9d, 1; unsigned __int16
0x1800384c7  lea     rdx, aCdefragoperati; "CDefragOperation::GetMoveSizeInBytes"
0x1800384ce  mov     r8d, 242h; unsigned __int16
0x1800384d4  lea     rcx, [rsp+98h+var_48]; this
0x1800384d9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800384de  lea     rax, [rsp+98h+hKey]
0x1800384e6  mov     ebx, 80h
0x1800384eb  mov     [rsp+98h+var_58], rax; PHKEY
0x1800384f0  lea     r8, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Dfrg"
0x1800384f7  lea     rcx, aDfrg_1; "Dfrg"
0x1800384fe  mov     [rsp+98h+var_68], 20019h; REGSAM
0x180038506  mov     [rsp+98h+hKey], 0
0x180038512  mov     [rsp+98h+arg_0], ebx
0x180038519  call    ?SxRegCreateKeyExStateSeparated@@YAJPEBGPEAUHKEY__@@0KPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SxRegCreateKeyExStateSeparated(ushort const *,HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18003851e  test    eax, eax
0x180038520  js      short loc_180038565
0x180038522  mov     rcx, [rsp+98h+hKey]; hKey
0x18003852a  lea     r8, [rsp+98h+arg_0]; unsigned int *
0x180038532  mov     r9d, 1; int
0x180038538  lea     rdx, aMovesizekb; "MoveSizeKB"
0x18003853f  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180038544  mov     ebx, [rsp+98h+arg_0]
0x18003854b  cmp     ebx, 10000h
0x180038551  jbe     short loc_18003855A
0x180038553  mov     ebx, 4000000h
0x180038558  jmp     short loc_180038569
0x18003855a  test    ebx, ebx
0x18003855c  jnz     short loc_180038565
0x18003855e  mov     ebx, 20000h
0x180038563  jmp     short loc_180038569
0x180038565  shl     rbx, 0Ah
0x180038569  mov     rcx, [rsp+98h+hKey]; hKey
0x180038571  lea     rdx, [rcx-1]
0x180038575  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180038579  ja      short loc_18003858D
0x18003857b  call    cs:__imp_RegCloseKey
0x180038581  mov     [rsp+98h+hKey], 0
0x18003858d  lea     rcx, [rsp+98h+var_48]; this
0x180038592  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180038597  mov     rax, rbx
0x18003859a  add     rsp, 90h
0x1800385a1  pop     rbx
0x1800385a2  retn
```
