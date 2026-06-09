# ChannelStateTxt

- ea: `0x1400105ec`
- end: `0x140010681`
- name: `ChannelStateTxt`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400197ec`
- `0x140019cd0`
- `0x14001a164`

## callees

- `0x1400105ec`

## string_xrefs

- `0x14001062f`: `STATE_CHANNEL_CREATED`

## pseudocode

```c
const char *__fastcall ChannelStateTxt(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx

  if ( a1 <= 5 )
  {
    if ( a1 == 5 )
      return "STATE_CHANNEL_ACTIVE";
    if ( !a1 )
      return "STATE_CHANNEL_CREATED";
    v1 = a1 - 1;
    if ( !v1 )
      return "STATE_CHANNEL_NEGOTIATE_MTU";
    v2 = v1 - 1;
    if ( !v2 )
      return "STATE_CHANNEL_SENT_SABM";
    v3 = v2 - 1;
    if ( !v3 )
      return "STATE_CHANNEL_GOT_SABM";
    if ( v3 == 1 )
      return "STATE_CHANNEL_EXCHANGE_MSC";
    return "INVALID STATE";
  }
  v5 = a1 - 6;
  if ( !v5 )
    return "STATE_CHANNEL_CLOSING_FLUSH_EXCHANGE_MSC";
  v6 = v5 - 1;
  if ( !v6 )
    return "STATE_CHANNEL_CLOSING_FLUSH";
  v7 = v6 - 1;
  if ( !v7 )
    return "STATE_CHANNEL_CLOSING";
  if ( v7 != 1 )
    return "INVALID STATE";
  return "STATE_CHANNEL_DEAD";
}

```

## disassembly

```asm
0x1400105ec  cmp     ecx, 5
0x1400105ef  jg      short loc_140010641
0x1400105f1  jz      short loc_140010638
0x1400105f3  test    ecx, ecx
0x1400105f5  jz      short loc_14001062F
0x1400105f7  sub     ecx, 1
0x1400105fa  jz      short loc_140010626
0x1400105fc  sub     ecx, 1
0x1400105ff  jz      short loc_14001061D
0x140010601  sub     ecx, 1
0x140010604  jz      short loc_140010614
0x140010606  cmp     ecx, 1
0x140010609  jnz     short loc_140010655
0x14001060b  lea     rax, aStateChannelEx; "STATE_CHANNEL_EXCHANGE_MSC"
0x140010612  retn
0x140010614  lea     rax, aStateChannelGo; "STATE_CHANNEL_GOT_SABM"
0x14001061b  retn
0x14001061d  lea     rax, aStateChannelSe; "STATE_CHANNEL_SENT_SABM"
0x140010624  retn
0x140010626  lea     rax, aStateChannelNe; "STATE_CHANNEL_NEGOTIATE_MTU"
0x14001062d  retn
0x14001062f  lea     rax, aStateChannelCr; "STATE_CHANNEL_CREATED"
0x140010636  retn
0x140010638  lea     rax, aStateChannelAc; "STATE_CHANNEL_ACTIVE"
0x14001063f  retn
0x140010641  sub     ecx, 6
0x140010644  jz      short loc_140010679
0x140010646  sub     ecx, 1
0x140010649  jz      short loc_140010670
0x14001064b  sub     ecx, 1
0x14001064e  jz      short loc_140010667
0x140010650  cmp     ecx, 1
0x140010653  jz      short loc_14001065E
0x140010655  lea     rax, aInvalidState; "INVALID STATE"
0x14001065c  retn
0x14001065e  lea     rax, aStateChannelDe; "STATE_CHANNEL_DEAD"
0x140010665  retn
0x140010667  lea     rax, aStateChannelCl_0; "STATE_CHANNEL_CLOSING"
0x14001066e  retn
0x140010670  lea     rax, aStateChannelCl; "STATE_CHANNEL_CLOSING_FLUSH"
0x140010677  retn
0x140010679  lea     rax, aStateChannelCl_1; "STATE_CHANNEL_CLOSING_FLUSH_EXCHANGE_MS"...
0x140010680  retn
```
