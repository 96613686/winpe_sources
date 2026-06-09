# Microsoft.Crm.Application.Script::BuildRedirectWithId_0

- ea: `0x16d80`
- end: `0x16dea`
- name: `Microsoft.Crm.Application.Script::BuildRedirectWithId_0`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x16d70`

## callees

- `0x16df0`
- `0x16e30`
- `0x16f20`
- `0x2fb90`
- `0x39f50`

## string_xrefs

- `0x16dca`: `/_common/global.ashx`
- `0x16d85`: `<!DOCTYPE html>\n							<html>\n							<head>\n							<script type='text/javascript' src='{4}'></script>\n							<script type="text/javascript">\n														{0} {3}\n\n							var sLocation = location.href;\n							if(sLocation.charAt(sLocation.length-1) === '#'){{sLocation = sLocation.slice(0, sLocation.length-1);}}\n							var sQuery = '';\n							var iQueryIndex = sLocation.indexOf('?');\n\n							// remove '#' char at the end of location href string for the correct work of Chro`

## pseudocode

```c

```
