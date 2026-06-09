# RfcommStateTxt

- ea: `0x140015bdc`
- end: `0x140015c45`
- name: `RfcommStateTxt`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001291c`
- `0x1400157dc`
- `0x140017ab8`
- `0x140017db4`
- `0x140018040`

## callees

- `0x140015bdc`

## string_xrefs

- `0x140015c3d`: `STATE_SESSION_CREATED`

## pseudocode

```c
const char *__fastcall RfcommStateTxt(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx

  if ( !a1 )
    return "STATE_SESSION_CREATED";
  v1 = a1 - 1;
  if ( !v1 )
    return "STATE_SESSION_CONNECTING";
  v2 = v1 - 1;
  if ( !v2 )
    return "STATE_SESSION_NEGOTIATE_DLCI0";
  v3 = v2 - 1;
  if ( !v3 )
    return "STATE_SESSION_WAIT_DLCI0";
  v4 = v3 - 1;
  if ( !v4 )
    return "STATE_SESSION_ACTIVE";
  v5 = v4 - 1;
  if ( !v5 )
    return "STATE_SESSION_DISCONNECTING";
  if ( v5 == 1 )
    return "STATE_SESSION_DEAD";
  return "INVALID STATE";
}

```

## disassembly

```asm
0x140015bdc  test    ecx, ecx
0x140015bde  jz      short loc_140015C3D
0x140015be0  sub     ecx, 1
0x140015be3  jz      short loc_140015C34
0x140015be5  sub     ecx, 1
0x140015be8  jz      short loc_140015C2B
0x140015bea  sub     ecx, 1
0x140015bed  jz      short loc_140015C22
0x140015bef  sub     ecx, 1
0x140015bf2  jz      short loc_140015C19
0x140015bf4  sub     ecx, 1
0x140015bf7  jz      short loc_140015C10
0x140015bf9  cmp     ecx, 1
0x140015bfc  jz      short loc_140015C07
0x140015bfe  lea     rax, aInvalidState; "INVALID STATE"
0x140015c05  retn
0x140015c07  lea     rax, aStateSessionDe; "STATE_SESSION_DEAD"
0x140015c0e  retn
0x140015c10  lea     rax, aStateSessionDi; "STATE_SESSION_DISCONNECTING"
0x140015c17  retn
0x140015c19  lea     rax, aStateSessionAc; "STATE_SESSION_ACTIVE"
0x140015c20  retn
0x140015c22  lea     rax, aStateSessionWa; "STATE_SESSION_WAIT_DLCI0"
0x140015c29  retn
0x140015c2b  lea     rax, aStateSessionNe; "STATE_SESSION_NEGOTIATE_DLCI0"
0x140015c32  retn
0x140015c34  lea     rax, aStateSessionCo; "STATE_SESSION_CONNECTING"
0x140015c3b  retn
0x140015c3d  lea     rax, aStateSessionCr; "STATE_SESSION_CREATED"
0x140015c44  retn
```
