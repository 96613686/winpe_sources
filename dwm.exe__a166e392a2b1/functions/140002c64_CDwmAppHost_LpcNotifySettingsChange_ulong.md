# CDwmAppHost::LpcNotifySettingsChange(ulong)

- ea: `0x140002c64`
- end: `0x140002ce7`
- name: `?LpcNotifySettingsChange@CDwmAppHost@@AEAAJK@Z`
- size: `131`
- prototype: `__int64 __fastcall(CDwmAppHost *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002630`
- `0x140002850`
- `0x140002c1c`
- `0x1400038d4`
- `0x140003a00`

## callees

- `0x140002c64`
- `0x140002cf0`
- `0x140002e24`
- `0x140002e6c`
- `0x14000da20`

## pseudocode

```c
__int64 __fastcall CDwmAppHost::LpcNotifySettingsChange(CDwmAppHost *this)
{
  unsigned int v1; // ebx
  int v2; // edx
  signed int v3; // eax
  _BYTE v5[16]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]
  CDwmAppHost *v7; // [rsp+60h] [rbp+8h] BYREF

  v7 = this;
  v1 = 0;
  if ( *(&hInstance + 1) )
  {
    CPortClient::CPortClient((CPortClient *)v5);
    v6 = (__int64)*(&hInstance + 1);
    LODWORD(v7) = 1073741871;
    HIDWORD(v7) = v2;
    v3 = CPortClient::SendComplexAsyncRequest((CPortClient *)v5, 1073741871, &v7);
    v1 = v3;
    if ( v3 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x17Eu, 0);
    CPortClient::~CPortClient((CPortClient *)v5);
  }
  return v1;
}

```

## disassembly

```asm
0x140002c64  mov     [rsp+arg_0], rcx
0x140002c69  push    rbx
0x140002c6a  sub     rsp, 50h
0x140002c6e  xor     ebx, ebx
0x140002c70  cmp     qword ptr cs:hInstance+8, rbx
0x140002c77  jz      short loc_140002CDF
0x140002c79  lea     rcx, [rsp+58h+var_28]; this
0x140002c7e  call    ??0CPortClient@@QEAA@XZ; CPortClient::CPortClient(void)
0x140002c83  mov     rax, qword ptr cs:hInstance+8
0x140002c8a  lea     r8, [rsp+58h+arg_0]; void *
0x140002c8f  mov     ecx, 4000002Fh
0x140002c94  mov     [rsp+58h+var_18], rax
0x140002c99  mov     [rsp+58h+arg_0], rcx
0x140002c9e  mov     dword ptr [rsp+58h+arg_0+4], edx
0x140002ca2  mov     edx, ecx; unsigned int
0x140002ca4  lea     rcx, [rsp+58h+var_28]; this
0x140002ca9  call    ?SendComplexAsyncRequest@CPortClient@@QEAAJKPEBXF@Z; CPortClient::SendComplexAsyncRequest(ulong,void const *,short)
0x140002cae  mov     ebx, eax
0x140002cb0  test    eax, eax
0x140002cb2  jns     short loc_140002CD5
0x140002cb4  xor     edx, edx; int *
0x140002cb6  mov     [rsp+58h+var_30], 0; void *
0x140002cbf  mov     r9d, eax; int
0x140002cc2  mov     [rsp+58h+var_38], 17Eh; unsigned int
0x140002cca  xor     r8d, r8d; unsigned int
0x140002ccd  lea     ecx, [rdx+14h]; unsigned int
0x140002cd0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x140002cd5  lea     rcx, [rsp+58h+var_28]; this
0x140002cda  call    ??1CPortClient@@UEAA@XZ; CPortClient::~CPortClient(void)
0x140002cdf  mov     eax, ebx
0x140002ce1  add     rsp, 50h
0x140002ce5  pop     rbx
0x140002ce6  retn
```
